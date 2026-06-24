# Patrones de comunicación

> Estado: 🟢 Completo | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

## Objetivo

Definir los mecanismos de comunicación utilizados entre los microservicios del sistema Gestión de Horarios SENA, garantizando bajo acoplamiento, escalabilidad y resiliencia.

---

# Comunicación Síncrona

## REST (Patrón Principal)

La comunicación síncrona entre servicios se realizará mediante APIs REST.

### Uso

* Consultas de información.
* Operaciones CRUD.
* Validaciones de negocio.
* Solicitudes que requieren respuesta inmediata.

### Protocolo

* HTTP/HTTPS
* JSON

### Versionado

Las APIs deberán versionarse mediante URI:

```text
/api/v1/
```

Ejemplos:

```text
GET /api/v1/fichas/{id}
GET /api/v1/instructores/{id}
POST /api/v1/schedules
```

### Documentación

Toda API deberá documentarse mediante OpenAPI 3.0.

Ubicación:

```text
07-api/contracts/openapi/
```

---

## Casos de uso síncronos

### Consulta de Instructor

```text
Scheduling Service
    → Actors Service
    → Obtiene disponibilidad
```

### Consulta de Ambiente

```text
Scheduling Service
    → Training Environment Service
    → Obtiene disponibilidad del ambiente
```

### Consulta Académica

```text
Scheduling Service
    → Academic Management Service
    → Obtiene información de ficha, programa o competencia
```

---

# Comunicación Asíncrona

## Eventos de Dominio

La integración desacoplada entre servicios utilizará eventos de dominio.

### Objetivos

* Reducir acoplamiento.
* Permitir procesamiento en segundo plano.
* Facilitar auditoría y monitoreo.
* Sincronizar información entre dominios.

### Broker

La tecnología definitiva será seleccionada durante la fase de implementación.

Alternativas evaluadas:

* Apache Kafka
* Azure Service Bus

### Garantía

```text
At-Least-Once Delivery
```

### Formato de Evento

```json
{
  "eventId": "uuid",
  "eventType": "ScheduleCreated",
  "timestamp": "2026-06-24T10:00:00Z",
  "tenantId": "tenant-01",
  "source": "scheduling-service",
  "payload": {}
}
```

---

## Eventos principales

### IAM Service

Publica:

* UserCreated
* UserUpdated
* UserDisabled

---

### Academic Management Service

Publica:

* ProgramCreated
* CompetencyCreated
* LearningOutcomeCreated
* FichaCreated
* FichaUpdated

---

### Actors Service

Publica:

* InstructorAssigned
* InstructorUpdated

---

### Training Environment Service

Publica:

* EnvironmentCreated
* EnvironmentUpdated
* EnvironmentUnavailable

---

### Scheduling Service

Publica:

* ScheduleCreated
* ScheduleUpdated
* ScheduleCancelled
* ConflictDetected

---

### Document Service

Publica:

* DocumentCreated
* DocumentVersionCreated

---

### Monitoring Service

Publica:

* AlertGenerated
* KPICalculated

---

### Audit Service

Consume eventos de todos los servicios.

---

# Resiliencia y Tolerancia a Fallos

## Circuit Breaker

Objetivo:

Evitar cascadas de fallos entre servicios.

### Configuración inicial

* Activación: 3 errores consecutivos.
* Estado Open: 30 segundos.
* Recuperación automática mediante Half-Open.

---

## Retry

### Política

Exponential Backoff

```text
1s → 2s → 4s
```

### Máximo

```text
3 intentos
```

Aplica únicamente para errores transitorios.

---

## Timeout

| Comunicación      | Timeout                        |
| ----------------- | ------------------------------ |
| REST              | 30 segundos                    |
| Consulta interna  | 10 segundos                    |
| Broker de eventos | Gestionado por infraestructura |

---

## Dead Letter Queue (DLQ)

Los eventos que no puedan procesarse después de múltiples intentos deberán enviarse a una cola de errores.

### Retención

30 días.

### Monitoreo

Generar alerta cuando existan más de 5 mensajes fallidos por hora.

---

# Patrones por Caso de Uso

## Creación de Horario

```text
Usuario
    ↓
Scheduling Service
    ↓
Consulta Instructor
    ↓
Actors Service

Consulta Ambiente
    ↓
Training Environment Service

Consulta Información Académica
    ↓
Academic Management Service

Genera Horario
    ↓
Publica ScheduleCreated
```

---

## Modificación de Ficha

```text
Usuario
    ↓
Academic Management Service

Valida información
    ↓
Actualiza ficha
    ↓
Publica FichaUpdated
```

---

## Generación de Alerta

```text
Monitoring Service
    ↓
Publica AlertGenerated
    ↓
Audit Service registra evento
```

---

# Principios de Integración

* API First.
* Contract First.
* Event Driven Architecture.
* Consistencia eventual entre dominios.
* Comunicación desacoplada.
* Observabilidad obligatoria.
* Seguridad mediante JWT y OAuth2.

