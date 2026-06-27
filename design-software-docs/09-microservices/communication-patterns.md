# Patrones de comunicación

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Arquitectura

## Objetivo

Definir los mecanismos de comunicación entre los microservicios del sistema, garantizando bajo acoplamiento, escalabilidad y confiabilidad.

---

# Comunicación síncrona

La comunicación síncrona se realiza mediante **APIs REST**, utilizadas cuando un servicio requiere una respuesta inmediata de otro.

### Casos de uso

- Validar usuarios y permisos.
- Consultar información de instructores.
- Consultar disponibilidad de ambientes.
- Obtener información de programas y fichas.

---

# Comunicación asíncrona

La comunicación asíncrona se basa en **eventos de dominio**, permitiendo desacoplar procesos entre servicios.

### Casos de uso

- Registro de auditoría.
- Envío de notificaciones.
- Actualización de indicadores.
- Generación de documentos.

---

# Flujo general

```text
Cliente
    │
    ▼
API Gateway
    │
    ▼
Microservicios
    │
    ├── REST (consultas)
    │
    └── Eventos (procesos asíncronos)
```

---

# Resiliencia

Para garantizar la disponibilidad del sistema se implementan las siguientes estrategias:

- Reintentos automáticos (Retry).
- Tiempo máximo de espera (Timeout).
- Circuit Breaker.
- Registro centralizado de errores.

---

# Buenas prácticas

- Evitar llamadas innecesarias entre servicios.
- Publicar eventos únicamente cuando exista un cambio de negocio.
- Versionar las APIs.
- Mantener contratos de integración estables.
- Registrar las operaciones críticas para auditoría.

---

# Eventos principales

| Evento | Servicio origen | Servicios consumidores |
|---------|-----------------|-------------------------|
| UserCreated | IAM Service | Audit, Monitoring |
| ScheduleCreated | Scheduling Service | Monitoring, Document, Audit |
| ScheduleUpdated | Scheduling Service | Monitoring, Audit |
| EnvironmentUpdated | Training Environment Service | Scheduling |
| DocumentGenerated | Document Service | Audit |
| AlertGenerated | Monitoring Service | Document, Audit |

---

# Relación con otros documentos

- **07-api:** Contratos y convenciones de las APIs.
- **02-domain:** Eventos del dominio.
- **05-architecture:** Arquitectura general de integración.