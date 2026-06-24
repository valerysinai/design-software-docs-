# ADR-002: Estrategia Multi-Tenant

**Estado:** APPROVED
**Fecha:** 2026-06-22
**Autores:** Por definir
**Equipos involucrados:** Arquitectura, Desarrollo, Seguridad

---

## Contexto

La solución debe soportar múltiples centros de formación del SENA manteniendo separación lógica de la información y optimizando el uso de infraestructura.

Se requiere una estrategia que permita crecimiento institucional sin duplicar plataformas completas para cada centro.

## Decisión

Se decide implementar una estrategia Multi-Tenant lógica basada en identificadores de tenant.

Cada registro deberá estar asociado a un tenant_id que permita aislar la información de cada centro de formación.

La validación del tenant será obligatoria en todas las operaciones de negocio.

## Consecuencias

### Positivas

* Menor costo de infraestructura.
* Simplificación operativa.
* Escalabilidad institucional.

### Negativas / Trade-offs

* Mayor complejidad en la capa de seguridad.
* Necesidad de validaciones adicionales en cada operación.

### Riesgos

* Fuga de información entre tenants por errores de implementación.
* Consultas incorrectas si no se aplican filtros de tenant.

## Alternativas consideradas

| Alternativa                        | Por qué se descartó                                 |
| ---------------------------------- | --------------------------------------------------- |
| Base de datos por tenant           | Incrementa significativamente los costos operativos |
| Instancia independiente por tenant | Mayor complejidad de administración                 |

## Referencias

* ../../overview.md
* ../../cross-cutting.md
