# ADR-002: Estrategia Multi-Tenant

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

---

## Contexto

La plataforma **Gestión de Horarios SENA** será utilizada por diferentes regionales y centros de formación, por lo que es necesario garantizar el aislamiento lógico de la información perteneciente a cada unidad organizacional.

Se requiere una estrategia que permita compartir la infraestructura tecnológica sin comprometer la seguridad, la privacidad de los datos ni la independencia operativa de cada centro de formación.

---

## Decisión

Se adopta una estrategia **Multi-Tenant lógica**, basada en un identificador único (`tenant_id`) asociado a cada registro del sistema.

Cada microservicio será responsable de validar el `tenant_id` en todas las operaciones de consulta y modificación de datos.

Esta estrategia permitirá:

- Compartir la infraestructura entre múltiples centros de formación.
- Mantener el aislamiento lógico de la información.
- Facilitar la escalabilidad institucional.
- Simplificar la administración de la plataforma.

La autenticación y autorización garantizarán que cada usuario únicamente acceda a la información correspondiente a su tenant.

---

## Consecuencias

### Positivas

- Optimización del uso de infraestructura.
- Menores costos operativos.
- Escalabilidad para nuevos centros de formación.
- Administración centralizada de la plataforma.

### Negativas / Trade-offs

- Mayor complejidad en la capa de seguridad.
- Validaciones adicionales en todas las consultas y operaciones.
- Mayor cuidado en el diseño de las APIs.

### Riesgos

- Acceso indebido a información por errores en la validación del `tenant_id`.
- Consultas incorrectas si no se aplican filtros de aislamiento.
- Incremento de la complejidad en pruebas de seguridad.

---

## Alternativas consideradas

| Alternativa | Motivo del descarte |
|-------------|---------------------|
| Base de datos por tenant | Incrementa significativamente los costos de infraestructura y mantenimiento. |
| Instancia independiente por tenant | Dificulta la administración y el despliegue de la plataforma. |
| Esquema independiente por tenant | Aumenta la complejidad de administración y las migraciones de base de datos. |

---

## Impacto arquitectónico

### Componentes afectados

- API Gateway
- IAM Service
- Todos los microservicios
- Bases de datos

### Servicios afectados

La estrategia aplica a todos los servicios de la plataforma, especialmente:

- IAM Service
- Academic Management Service
- Actors Service
- Training Environment Service
- Scheduling Service
- Reference Data Service

### Datos afectados

Todas las entidades de negocio deberán almacenar el identificador `tenant_id` para garantizar el aislamiento lógico de la información.

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
- [../cross-cutting.md](../cross-cutting.md) — Aspectos transversales.
- [../../04-requirements/non-functional.md](../../04-requirements/non-functional.md) — Requisitos no funcionales.
- [../../02-domain/entities-and-rules/README.md](../../02-domain/entities-and-rules/README.md) — Reglas del dominio.