# Matriz de Propiedad de Datos

> Estado: 🟡 En progreso
>
> Última actualización: 2026-06-24
>
> Autor: Por definir
>
> Equipo: Arquitectura

---

# Objetivo

Definir la propiedad canónica de los datos dentro de la arquitectura de microservicios.

Cada servicio es responsable de:

* Crear sus datos.
* Actualizarlos.
* Garantizar su integridad.
* Publicar eventos cuando cambien.

Los demás servicios pueden:

* Consultarlos.
* Replicarlos mediante eventos.
* Mantener cachés locales.

Los demás servicios **no pueden modificarlos directamente**.

---

# Principio de Ownership

```text
Un dato tiene un único dueño.

Servicio dueño:
  ✓ CREATE
  ✓ UPDATE
  ✓ DELETE

Otros servicios:
  ✓ READ
  ✓ CACHE
  ✓ REPLICA

  ✗ UPDATE
  ✗ DELETE
```

---

# Matriz de Responsabilidades

## IAM Service

| Entidad | Dueño       | Consumidores | Réplicas |
| ------- | ----------- | ------------ | -------- |
| Usuario | iam-service | Todos        | Ninguna  |
| Rol     | iam-service | Todos        | Ninguna  |
| Permiso | iam-service | Todos        | Ninguna  |
| Sesión  | iam-service | iam-service  | Ninguna  |
| Token   | iam-service | iam-service  | Ninguna  |

---

## Reference Data Service

| Entidad   | Dueño                  | Consumidores | Réplicas    |
| --------- | ---------------------- | ------------ | ----------- |
| Centro    | reference-data-service | Todos        | Caché (24h) |
| Regional  | reference-data-service | Todos        | Caché (24h) |
| Parámetro | reference-data-service | Todos        | Caché (1h)  |

---

## Academic Management Service

| Entidad          | Dueño            | Consumidores     | Réplicas                                               |
| ---------------- | ---------------- | ---------------- | ------------------------------------------------------ |
| Programa         | academic-service | Todos            | scheduling-service                                     |
| Competencia      | academic-service | Todos            | scheduling-service, actors-service                     |
| RAP              | academic-service | Todos            | scheduling-service, document-service                   |
| Ficha            | academic-service | Todos            | scheduling-service, actors-service, monitoring-service |
| Oferta Formativa | academic-service | academic-service | Ninguna                                                |

---

## Training Environment Service

| Entidad        | Dueño               | Consumidores                           | Réplicas                   |
| -------------- | ------------------- | -------------------------------------- | -------------------------- |
| Ambiente       | environment-service | Todos                                  | scheduling-service (caché) |
| Disponibilidad | environment-service | scheduling-service, monitoring-service | Ninguna                    |
| Inventario     | environment-service | environment-service                    | Ninguna                    |
| Mantenimiento  | environment-service | scheduling-service                     | Ninguna                    |

---

## Scheduling Service

| Entidad         | Dueño              | Consumidores                           | Réplicas                             |
| --------------- | ------------------ | -------------------------------------- | ------------------------------------ |
| Horario         | scheduling-service | Todos                                  | monitoring-service, document-service |
| Sesión de Clase | scheduling-service | Todos                                  | monitoring-service, document-service |
| Conflicto       | scheduling-service | scheduling-service, monitoring-service | Ninguna                              |
| Franja Horaria  | scheduling-service | Todos                                  | Caché (24h)                          |

---

## Actors Service

| Entidad          | Dueño          | Consumidores     | Réplicas                               |
| ---------------- | -------------- | ---------------- | -------------------------------------- |
| Instructor       | actors-service | Todos            | scheduling-service, monitoring-service |
| Aprendiz         | actors-service | Todos            | academic-service, scheduling-service   |
| Empresa          | actors-service | Todos            | academic-service                       |
| Etapa Productiva | actors-service | academic-service | Ninguna                                |

---

## Document Service

| Entidad   | Dueño            | Consumidores     | Réplicas |
| --------- | ---------------- | ---------------- | -------- |
| Plantilla | document-service | document-service | Ninguna  |
| Documento | document-service | document-service | Ninguna  |
| Versión   | document-service | document-service | Ninguna  |

---

## Monitoring Service

| Entidad      | Dueño              | Consumidores                 | Réplicas   |
| ------------ | ------------------ | ---------------------------- | ---------- |
| KPI          | monitoring-service | Todos                        | Caché (1h) |
| Alerta       | monitoring-service | monitoring-service, usuarios | Ninguna    |
| Notificación | monitoring-service | usuarios                     | Ninguna    |

---

## Audit Service

| Entidad               | Dueño         | Consumidores              | Réplicas              |
| --------------------- | ------------- | ------------------------- | --------------------- |
| Registro de Auditoría | audit-service | audit-service, compliance | Ninguna (append-only) |

---

# Reglas de Acceso a Datos

## Lectura de Datos

Los servicios pueden acceder a datos externos únicamente mediante mecanismos autorizados:

### API REST

```http
GET /api/v1/resource/{id}
```

### gRPC

```proto
rpc GetResource(ReadRequest) returns (ResourceResponse);
```

### Réplicas por Eventos

```text
Servicio A publica evento
        ↓
Servicio B consume evento
        ↓
Actualiza réplica local
```

---

## Restricciones

### Acceso Directo a Bases de Datos

No está permitido acceder directamente a bases de datos de otros servicios.

```sql
-- ❌ Incorrecto

SELECT *
FROM academic_db.ficha;
```

---

### Escritura Remota

No está permitido modificar datos de otro servicio mediante acceso directo.

```http
# ❌ Incorrecto

PATCH /academic-service/fichas/F123
```

---

### Transacciones Distribuidas

No se permiten transacciones que involucren múltiples bases de datos.

```text
Servicio A
   ├── BD A
   └── BD B   ❌
```

Cada servicio mantiene consistencia local y coordinación mediante eventos.

---

# Modificación de Datos Entre Servicios

Cuando un servicio requiere que otro modifique información:

## Opción 1: API del Servicio Dueño

```text
Servicio A
      │
      ▼
POST /api/v1/recurso
      │
      ▼
Servicio B
```

## Opción 2: Comunicación Basada en Eventos

```text
Servicio A
      │
      ▼
Publica Evento
      │
      ▼
Broker
      │
      ▼
Servicio B
```

---

# Ejemplos de Interacción

## Scheduling Consulta Competencias

```text
POST /schedules

Datos recibidos:

- fichaId
- instructorId
- rapId

Proceso:

1. Consulta réplica local
2. Valida existencia del RAP
3. Si es necesario consulta academic-service
4. Genera horario
5. Publica evento ScheduleCreated
```

---

## Monitoring Calcula KPIs

```text
GET /kpis

Proceso:

1. Consulta KPI precalculado
2. Si está desactualizado:
   - Consulta academic-service
   - Consulta scheduling-service
   - Consulta actors-service
3. Recalcula métricas
4. Guarda resultado local
5. Responde solicitud
```

---

## Generación de Certificados

```text
POST /documents/certificates

Proceso:

1. Obtiene plantilla
2. Consulta ficha
3. Consulta aprendiz
4. Consulta resultados académicos
5. Genera PDF
6. Almacena documento
7. Publica evento DocumentGenerated
```

---

# Estrategia de Sincronización

## Datos Cacheables

| Dato                      | TTL | Evento de Invalidación | Cambio Crítico |
| ------------------------- | --- | ---------------------- | -------------- |
| Centros                   | 24h | CentroActualizado      | No             |
| Parámetros                | 1h  | ParametroActualizado   | Sí             |
| Competencias              | 4h  | CompetenciaActualizada | Sí             |
| Disponibilidad Instructor | 30m | InstructorActualizado  | Sí             |
| Ambientes                 | 4h  | AmbienteActualizado    | No             |

---

## Patrón de Invalidación

```text
Academic Service
      │
      ▼
CompetenciaActualizada
      │
      ▼
Event Bus
      │
 ┌────┼────┐
 ▼    ▼    ▼

Scheduling
Monitoring
Document

→ Invalidan caché local
→ Obtienen nueva versión
```
