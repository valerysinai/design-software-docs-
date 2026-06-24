# ADR-005: Comunicación entre servicios

**Estado:** APPROVED
**Fecha:** 2026-06-24
**Autores:** Por definir
**Equipos involucrados:** Arquitectura, Desarrollo, DevOps

---

## Contexto

Los microservicios deben intercambiar información para ejecutar procesos académicos y administrativos.

Algunas operaciones requieren respuestas inmediatas y otras pueden ejecutarse de forma asíncrona.

## Decisión

Se decide utilizar una estrategia híbrida de integración:

* REST para comunicación sincrónica.
* Eventos para comunicación asíncrona.

REST será utilizado para consultas y operaciones transaccionales.

Los eventos serán utilizados para auditoría, monitoreo, notificaciones y sincronización de procesos.

Eventos iniciales:

* UserCreated
* UserUpdated
* InstructorAssigned
* ScheduleCreated
* ScheduleUpdated
* IncidentReported

## Consecuencias

### Positivas

* Menor acoplamiento entre servicios.
* Mayor escalabilidad.
* Flexibilidad de integración.

### Negativas / Trade-offs

* Incremento de complejidad en la infraestructura.
* Necesidad de administrar mensajería y eventos.

### Riesgos

* Pérdida de eventos si no existen mecanismos de recuperación.
* Consistencia eventual entre dominios.

## Alternativas consideradas

| Alternativa  | Por qué se descartó                   |
| ------------ | ------------------------------------- |
| Solo REST    | Incrementa el acoplamiento temporal   |
| Solo eventos | No adecuado para consultas inmediatas |

## Referencias

* ../../cross-cutting.md
* ADR-001-arquitectura-microservicios.md
