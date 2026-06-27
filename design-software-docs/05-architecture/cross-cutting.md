# Aspectos Transversales de la Arquitectura

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por derfinir

## Objetivo

Describir los componentes y principios transversales que aplican a toda la arquitectura del sistema, independientemente del dominio de negocio al que pertenezca cada microservicio.

---

# Seguridad

La seguridad es un aspecto transversal presente en todos los servicios de la plataforma.

## Autenticación

Se implementará mediante:

- JWT (JSON Web Token).
- OAuth2 / OpenID Connect.
- Refresh Tokens.

## Autorización

El acceso a los recursos será controlado mediante:

- RBAC (Role-Based Access Control).
- Validación centralizada de permisos.
- Verificación de roles antes de ejecutar operaciones.

## Protección de datos

Se aplicarán las siguientes medidas:

- Comunicación cifrada mediante TLS 1.3.
- Cifrado de información sensible.
- Gestión segura de secretos y credenciales.
- Protección de datos personales conforme a la normativa vigente.

---

# Auditoría

Todos los microservicios deberán registrar las operaciones críticas ejecutadas por los usuarios.

Cada registro de auditoría deberá incluir como mínimo:

- Usuario responsable.
- Fecha y hora.
- Operación ejecutada.
- Servicio origen.
- Recurso afectado.
- Resultado de la operación.
- Correlation ID.

Los registros serán de solo escritura (append-only) y no podrán modificarse posteriormente.

---

# Observabilidad

La plataforma incorporará mecanismos para facilitar el monitoreo y diagnóstico de los servicios.

## Logging

Todos los servicios generarán logs estructurados y centralizados.

## Métricas

Se recopilarán indicadores como:

- Uso de CPU.
- Uso de memoria.
- Tiempo de respuesta.
- Latencia.
- Número de errores.
- Disponibilidad del servicio.

## Trazabilidad distribuida

Todas las solicitudes propagarán un **Correlation ID** para rastrear el flujo completo entre microservicios.

---

# Gestión de errores

Todos los servicios implementarán un mecanismo uniforme para el manejo de excepciones.

Las respuestas de error deberán contener información estandarizada.

Ejemplo:

```json
{
  "code": "SCH-001",
  "message": "Conflicto de horario detectado",
  "timestamp": "2026-06-24T10:00:00Z"
}
```

---

# Integración entre servicios

La comunicación entre microservicios podrá realizarse mediante dos mecanismos.

## Comunicación síncrona

- APIs REST.
- Contratos documentados mediante OpenAPI.

## Comunicación asíncrona

Mediante eventos publicados en el Message Broker.

Ejemplos de eventos:

- UserCreated
- InstructorAssigned
- ScheduleCreated
- ScheduleUpdated
- SessionCompleted

---

# Calidad

Todos los componentes deberán cumplir los estándares definidos por el proyecto.

## Pruebas

Se contemplan:

- Pruebas unitarias.
- Pruebas de integración.
- Pruebas de contratos.
- Pruebas End-to-End.

## Cobertura

Cobertura mínima esperada:

- 80 % del código.

## Documentación

Todas las APIs deberán documentarse mediante OpenAPI 3.0 y mantenerse sincronizadas con su implementación.

---

# Principios transversales

Toda la solución deberá cumplir los siguientes principios:

- Seguridad por defecto.
- Observabilidad desde el diseño.
- Bajo acoplamiento entre servicios.
- Alta cohesión por dominio.
- Trazabilidad de extremo a extremo.
- Database per Service.
- API First.
- Event-Driven Architecture.

---

# Referencias

- [overview.md](./overview.md) — Vista general de arquitectura.
- [deployment.md](./deployment.md) — Arquitectura de despliegue.
- [../04-requirements/non-functional.md](../04-requirements/non-functional.md) — Requisitos no funcionales.
- [../02-domain/domain-events/README.md](../02-domain/domain-events/README.md) — Eventos del dominio.