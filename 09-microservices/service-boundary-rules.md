# Reglas de límites de servicio

> Estado: 🟢 Completo | Última actualización: 2026-06-23
> Autor: Por definir | Equipo: Por definir# Reglas de Límites de Servicio

---

# Objetivo

Definir las reglas arquitectónicas que delimitan las responsabilidades de cada microservicio y garantizan el desacoplamiento, la escalabilidad y la mantenibilidad del sistema.

---

# Principios Generales

## Responsabilidad Única

Cada microservicio debe representar un único dominio de negocio.

| Servicio               | Dominio                  |
| ---------------------- | ------------------------ |
| iam-service            | Identidad y acceso       |
| reference-data-service | Datos maestros           |
| academic-service       | Gestión académica        |
| environment-service    | Ambientes de formación   |
| scheduling-service     | Programación de horarios |
| actors-service         | Gestión de actores       |
| document-service       | Gestión documental       |
| monitoring-service     | KPIs y monitoreo         |
| audit-service          | Auditoría                |

---

## Ownership de Datos

Cada entidad tiene un único dueño.

```text
Programa
    ↓
academic-service

Instructor
    ↓
actors-service

Horario
    ↓
scheduling-service
```

El servicio propietario es el único autorizado para:

* Crear registros.
* Modificar registros.
* Eliminar registros.
* Definir reglas de negocio sobre la entidad.

---

## Base de Datos por Servicio

Cada servicio mantiene una base de datos independiente.

```text
academic-service
    └── academic_db

actors-service
    └── actors_db

scheduling-service
    └── scheduling_db
```

No se permite compartir bases de datos.

---

# Comunicación Entre Servicios

## Comunicación Sincrónica

Permitida para consultas de información.

### REST

```http
GET /api/v1/programs/{id}
```

### gRPC

```proto
rpc GetProgram(GetProgramRequest)
returns (ProgramResponse);
```

---

## Comunicación Asincrónica

Utilizada para propagación de cambios.

```text
academic-service
       │
       ▼
ProgramCreated
       │
       ▼
Event Bus
       │
       ▼
scheduling-service
```

---

# Restricciones

## Acceso Directo a Datos

No está permitido acceder directamente a bases de datos externas.

```sql
-- ❌ Incorrecto

SELECT *
FROM academic_db.programs;
```

---

## Escritura Cruzada

No está permitido modificar entidades de otro servicio.

```http
# ❌ Incorrecto

PATCH /academic-service/programs/P001
```

La modificación debe realizarse mediante:

* API pública del servicio dueño.
* Eventos de dominio.

---

## Entidades Compartidas

No se permite reutilizar entidades de dominio entre servicios.

```java
// ❌ Incorrecto

InstructorEntity
ProgramEntity
ScheduleEntity
```

Cada servicio define sus propios modelos internos.

---

## Transacciones Distribuidas

No se permiten transacciones que involucren múltiples bases de datos.

```text
Servicio A
   ├── BD A
   └── BD B   ❌
```

La consistencia entre servicios debe lograrse mediante eventos.

---

# Gestión de Réplicas

Los servicios pueden mantener:

* Cachés locales.
* Proyecciones de lectura.
* Réplicas derivadas de eventos.

Ejemplo:

```text
academic-service
      │
      ▼
CompetenciaActualizada
      │
      ▼
scheduling-service

Actualiza réplica local
```

La réplica nunca reemplaza al dueño canónico.

---

# Reglas de Evolución

## Versionado de APIs

Toda API pública debe estar versionada.

```text
/api/v1/programs
/api/v2/programs
```

---

## Versionado de Eventos

Los eventos deben incluir versión.

```text
academic.program.created.v1

academic.program.updated.v1

scheduling.schedule.created.v1
```

---

# Checklist de Validación

Antes de crear un nuevo servicio verificar:

* [ ] Tiene una responsabilidad única.
* [ ] Posee su propia base de datos.
* [ ] No comparte entidades.
* [ ] Publica eventos de dominio.
* [ ] Consume APIs públicas.
* [ ] No requiere transacciones distribuidas.
* [ ] Tiene ownership claro de sus datos.
* [ ] Está alineado con un bounded context definido.
