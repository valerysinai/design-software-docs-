# UML

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Arquitectura

## Contenido

Esta carpeta reúne los diagramas UML utilizados para documentar la arquitectura, los procesos y el diseño del sistema **Gestión de Horarios SENA**.

Cada diagrama debe contar con un archivo fuente editable y una versión exportada para facilitar su consulta durante el desarrollo y mantenimiento del proyecto.

---

## Convenciones

- Los archivos fuente se almacenan en `diagrams/source/`.
- Las exportaciones se almacenan en `diagrams/exports/`.
- Se recomienda utilizar formato **PlantUML (.puml)** para las fuentes.
- Las exportaciones deben generarse preferiblemente en formato **SVG**.
- Los nombres de los archivos seguirán la convención:

```text
<dominio>-<tipo>.<ext>
```

Ejemplos:

```text
scheduling-use-case.puml
actors-class.puml
environment-sequence.puml
deployment-component.puml
```

Todos los diagramas deberán registrarse en `diagram-index.md`.

---

## Tipos de diagramas

| Tipo | Descripción |
|------|-------------|
| Casos de uso | Interacción entre actores y funcionalidades del sistema |
| Clases | Modelo estático de entidades y relaciones |
| Secuencia | Interacción entre componentes durante un proceso |
| Actividad | Flujo de ejecución de procesos |
| Estado | Cambios de estado de una entidad |
| Componentes | Organización de los microservicios y dependencias |
| Despliegue | Infraestructura y distribución física de los servicios |

---

## Estructura

| Carpeta | Descripción | Estado |
|---------|-------------|--------|
| [diagram-index.md](./diagram-index.md) | Inventario de diagramas UML | 🟡 |
| [diagrams/source/](./diagrams/source/) | Archivos fuente editables (.puml o .wsd) | 🟡 |
| [diagrams/exports/](./diagrams/exports/) | Diagramas exportados (.svg o .png) | 🟡 |

---

## Relación con otras carpetas

- **02-domain:** diagramas del modelo de dominio.
- **03-product:** diagramas de procesos funcionales.
- **05-architecture:** diagramas de componentes y despliegue.
- **09-microservices:** diagramas específicos de cada servicio.

Los diagramas deben mantenerse sincronizados con la documentación funcional y arquitectónica del proyecto.