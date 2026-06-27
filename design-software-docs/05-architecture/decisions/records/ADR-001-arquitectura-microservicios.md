# ADR-001: Arquitectura basada en microservicios

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

---

## Contexto

La plataforma **Gestión de Horarios SENA** integra múltiples dominios de negocio, entre ellos autenticación, gestión académica, programación de horarios, administración de ambientes, monitoreo, documentación y auditoría.

Debido a la diversidad de responsabilidades y al crecimiento esperado del sistema, se requiere una arquitectura que permita desarrollar, desplegar y escalar cada dominio de manera independiente, manteniendo un bajo acoplamiento entre los componentes.

---

## Decisión

Se adopta una **arquitectura basada en microservicios**, organizada por dominios de negocio siguiendo principios de **Domain-Driven Design (DDD)**.

Cada microservicio será responsable de:

- Su propia lógica de negocio.
- Su base de datos (Database per Service).
- Sus contratos de integración.
- La publicación y consumo de eventos cuando sea necesario.

Los servicios definidos inicialmente son:

- IAM Service
- Academic Management Service
- Actors Service
- Training Environment Service
- Scheduling Service
- Reference Data Service
- Monitoring Service
- Document Service
- Audit Service

La comunicación entre servicios se realizará mediante APIs REST y eventos de dominio, dependiendo del tipo de integración requerida.

---

## Consecuencias

### Positivas

- Escalabilidad independiente de cada dominio.
- Bajo acoplamiento entre servicios.
- Despliegues independientes.
- Mayor mantenibilidad.
- Facilita la evolución futura de la plataforma.

### Negativas / Trade-offs

- Mayor complejidad en la infraestructura.
- Incremento en la comunicación distribuida.
- Mayor necesidad de monitoreo y observabilidad.

### Riesgos

- Consistencia de datos entre servicios.
- Mayor complejidad en el diagnóstico de errores distribuidos.
- Dependencia de una adecuada estrategia de integración.

---

## Alternativas consideradas

| Alternativa | Motivo del descarte |
|-------------|---------------------|
| Monolito tradicional | Dificulta el crecimiento independiente de los módulos. |
| Monolito modular | Reduce el acoplamiento, pero limita el despliegue y escalabilidad independiente. |
| Arquitectura orientada a servicios (SOA) | Introduce mayor complejidad de integración para el alcance actual del proyecto. |

---

## Impacto arquitectónico

### Componentes afectados

- API Gateway
- Todos los microservicios
- Message Broker
- Sistema de monitoreo

### Servicios afectados

- IAM Service
- Academic Management Service
- Actors Service
- Training Environment Service
- Scheduling Service
- Reference Data Service
- Monitoring Service
- Document Service
- Audit Service

### Datos afectados

Cada servicio mantiene la propiedad exclusiva de su información mediante el patrón **Database per Service**.

---

## Estado de implementación

| Actividad | Estado |
|-----------|--------|
| Diseño | ☑ |
| Desarrollo | ☐ |
| Pruebas | ☐ |
| Producción | ☐ |

---

## Referencias

- [../overview.md](../overview.md) — Vista general de arquitectura.
- [../deployment.md](../deployment.md) — Arquitectura de despliegue.
- [../cross-cutting.md](../cross-cutting.md) — Aspectos transversales.
- [../../02-domain/domain-map.md](../../02-domain/domain-map.md) — Mapa del dominio.