# Índice de diagramas UML

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Registrar los diagramas UML utilizados para documentar la arquitectura, el dominio y los procesos del sistema **Gestión de Horarios SENA**.

Cada diagrama debe contar con:

- Archivo fuente editable.
- Archivo exportado.
- Responsable de mantenimiento.
- Estado de actualización.

---

# Diagramas planificados

| Diagrama | Tipo | Fuente | Exportación | Estado |
|----------|------|---------|-------------|--------|
| Casos de uso del sistema | Casos de uso | `diagrams/source/system-use-case.puml` | `diagrams/exports/system-use-case.svg` | 🟡 |
| Modelo de dominio | Clases | `diagrams/source/domain-class.puml` | `diagrams/exports/domain-class.svg` | 🟡 |
| Programación de horarios | Secuencia | `diagrams/source/scheduling-sequence.puml` | `diagrams/exports/scheduling-sequence.svg` | 🟡 |
| Gestión de ambientes | Actividad | `diagrams/source/environment-activity.puml` | `diagrams/exports/environment-activity.svg` | 🟡 |
| Estados del horario | Estado | `diagrams/source/schedule-state.puml` | `diagrams/exports/schedule-state.svg` | 🟡 |
| Arquitectura de microservicios | Componentes | `diagrams/source/microservices-component.puml` | `diagrams/exports/microservices-component.svg` | 🟡 |
| Arquitectura de despliegue | Despliegue | `diagrams/source/deployment-diagram.puml` | `diagrams/exports/deployment-diagram.svg` | 🟡 |

---

# Convenciones

- Todos los diagramas deben elaborarse utilizando PlantUML o una herramienta compatible.
- Los archivos fuente deberán mantenerse actualizados con respecto a la documentación del proyecto.
- Las exportaciones deberán generarse en formato SVG siempre que sea posible.
- Los nombres de los archivos deben seguir una convención uniforme para facilitar su identificación.

---

# Organización de carpetas

```text
08-uml/
│
├── README.md
├── diagram-index.md
│
└── diagrams/
    ├── source/
    │   ├── system-use-case.puml
    │   ├── domain-class.puml
    │   ├── scheduling-sequence.puml
    │   ├── environment-activity.puml
    │   ├── schedule-state.puml
    │   ├── microservices-component.puml
    │   └── deployment-diagram.puml
    │
    └── exports/
        ├── system-use-case.svg
        ├── domain-class.svg
        ├── scheduling-sequence.svg
        ├── environment-activity.svg
        ├── schedule-state.svg
        ├── microservices-component.svg
        └── deployment-diagram.svg
```

---

# Relación con la documentación

Los diagramas documentan visualmente la información descrita en:

- `02-domain/`
- `03-product/`
- `04-requirements/`
- `05-architecture/`

Toda modificación relevante en la arquitectura o en los procesos del negocio debe reflejarse en los diagramas correspondientes.