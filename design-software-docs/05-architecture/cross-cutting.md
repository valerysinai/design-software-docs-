# Aspectos Transversales

> Estado: 🟢 Completo | Última actualización: 2026-06-22
> Autor: Por definir

## Seguridad

### Autenticación

* JWT.
* OAuth2/OpenID Connect.
* Refresh Tokens.

### Autorización

* RBAC (Role-Based Access Control).
* Validación centralizada de permisos.

### Protección de Datos

* TLS 1.3.
* Cifrado de información sensible.
* Gestión segura de secretos.

---

## Auditoría

Todos los servicios deberán generar eventos auditables.

Cada evento incluirá:

* Usuario.
* Fecha y hora.
* Operación.
* Servicio origen.
* Recurso afectado.
* Resultado.

---

## Observabilidad

### Logging

Logs estructurados centralizados.

### Métricas

* Uso de CPU.
* Uso de memoria.
* Latencia.
* Errores.

### Trazabilidad

Correlation ID para seguimiento entre servicios.

---

## Gestión de Errores

Todos los servicios implementarán:

* Manejo global de excepciones.
* Respuestas estandarizadas.
* Catálogo de errores.

Formato:

```json
{
  "code": "SCH-001",
  "message": "Conflicto de horario detectado",
  "timestamp": "2026-06-24T10:00:00Z"
}
```

---

## Integración

### Sincrónica

REST API.

### Asíncrona

Mensajería basada en eventos.

Eventos típicos:

* UserCreated
* InstructorAssigned
* ScheduleCreated
* ScheduleUpdated

---

## Calidad

### Pruebas

* Unitarias.
* Integración.
* Contratos.
* End-to-End.

### Cobertura

Cobertura mínima: 80%.

### Documentación

Todas las APIs deberán documentarse mediante OpenAPI 3.0.
