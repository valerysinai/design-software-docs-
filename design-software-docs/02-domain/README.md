# Dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Propósito

Esta carpeta documenta el **modelo de dominio** del Sistema de Gestión de Horarios del SENA.

Aquí se describen los **contextos del dominio**, las entidades principales, las reglas de negocio y los eventos que representan el comportamiento funcional del sistema. La documentación sigue los principios de **Domain-Driven Design (DDD)**, promoviendo una separación clara de responsabilidades y un lenguaje ubicuo compartido.

> **Diferencia con `06-data`:** esta sección describe el dominio desde la perspectiva del negocio (contextos, entidades, reglas y eventos). No define tablas, esquemas de base de datos ni detalles de implementación, los cuales se documentan en la carpeta [`06-data/`](../06-data/).

---

# Estructura

| Archivo                                      | Descripción                                                    | Estado |
| -------------------------------------------- | -------------------------------------------------------------- | ------ |
| [domain-map.md](./domain-map.md)             | Mapa de contextos del dominio y sus relaciones.                | 🟡     |
| [domain-events.md](./domain-events.md)       | Catálogo de eventos de dominio y comunicación entre contextos. | 🟡     |
| [01-identity.md](./01-identity.md)           | Contexto de Gestión de Identidad y Acceso.                     | 🟡     |
| [02-institutional.md](./02-institutional.md) | Contexto de Información Institucional.                         | 🟡     |
| [03-environments.md](./03-environments.md)   | Contexto de Gestión de Ambientes de Formación.                 | 🟡     |
| [04-academic.md](./04-academic.md)           | Contexto de Gestión Académica.                                 | 🟡     |
| [05-actors.md](./05-actors.md)               | Contexto de Gestión de Actores.                                | 🟡     |
| [06-scheduling.md](./06-scheduling.md)       | Contexto de Gestión de Horarios (Core Domain).                 | 🟡     |
| [07-monitoring.md](./07-monitoring.md)       | Contexto de Seguimiento y Monitoreo.                           | 🟡     |
| [08-documents.md](./08-documents.md)         | Contexto de Gestión Documental.                                | 🟡     |
| [09-audit.md](./09-audit.md)                 | Contexto de Auditoría y Trazabilidad.                          | 🟡     |
| [business-rules.md](./business-rules.md)     | Reglas generales del dominio aplicables a toda la plataforma.  | 🟢     |

