# ADR-001: Arquitectura basada en microservicios

**Estado:** APPROVED
**Fecha:** 2026-06-22
**Autores:** Por definir
**Equipos involucrados:** Arquitectura, Desarrollo, DevOps

---

## Contexto

El sistema Gestión de Horarios SENA debe soportar múltiples dominios funcionales como autenticación, gestión académica, programación de horarios, gestión de ambientes, auditoría y monitoreo.

Se requiere una arquitectura que permita la evolución independiente de los diferentes dominios, facilite el mantenimiento y soporte el crecimiento futuro de la plataforma.

## Decisión

Se decide adoptar una arquitectura basada en microservicios organizados por dominio de negocio.

Cada microservicio será responsable de su lógica de negocio, persistencia de datos y contratos de integración.

Los servicios identificados inicialmente son:

* IAM Service
* Academic Management Service
* Actors Service
* Training Environment Service
* Scheduling Service
* Reference Data Service
* Document Service
* Monitoring Service
* Audit Service

## Consecuencias

### Positivas

* Escalabilidad independiente por dominio.
* Menor acoplamiento entre componentes.
* Despliegues autónomos.
* Mejor mantenibilidad.

### Negativas / Trade-offs

* Mayor complejidad operativa.
* Incremento de la necesidad de monitoreo y observabilidad.
* Mayor complejidad en la integración de servicios.

### Riesgos

* Complejidad en la gestión de datos distribuidos.
* Sobrecarga operativa si no existe automatización adecuada.

## Alternativas consideradas

| Alternativa          | Por qué se descartó                                                           |
| -------------------- | ----------------------------------------------------------------------------- |
| Monolito tradicional | Limitaba la evolución independiente de módulos                                |
| Monolito modular     | Adecuado para etapas tempranas pero insuficiente para el crecimiento esperado |

## Referencias

* ../../overview.md
* ../../cross-cutting.md
