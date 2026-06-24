# ADR-004: Base de datos por servicio

**Estado:** APPROVED
**Fecha:** 2026-06-24
**Autores:** Por definir
**Equipos involucrados:** Arquitectura, Desarrollo

---

## Contexto

La arquitectura basada en microservicios requiere independencia entre dominios funcionales.

El uso de una base de datos compartida genera acoplamiento entre servicios y dificulta la evolución independiente.

## Decisión

Se decide implementar el patrón Database per Service.

Cada servicio será propietario exclusivo de su base de datos y de su modelo de persistencia.

No se permitirá acceso directo a bases de datos administradas por otros servicios.

## Consecuencias

### Positivas

* Independencia de despliegue.
* Menor acoplamiento.
* Evolución autónoma de esquemas.

### Negativas / Trade-offs

* Consultas distribuidas más complejas.
* Posible duplicación controlada de información.

### Riesgos

* Inconsistencia temporal entre servicios.
* Complejidad en reportes consolidados.

## Alternativas consideradas

| Alternativa              | Por qué se descartó                        |
| ------------------------ | ------------------------------------------ |
| Base de datos compartida | Genera dependencia directa entre servicios |

## Referencias

* ../../overview.md
* ADR-001-arquitectura-microservicios.md
