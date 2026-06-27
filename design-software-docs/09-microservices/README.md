# Microservicios

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Arquitectura

## Contenido

Esta carpeta reúne la documentación de los microservicios que conforman la arquitectura del sistema **Gestión de Horarios SENA**.

Cada microservicio representa un dominio de negocio independiente, con responsabilidades, base de datos y contratos de integración propios.

---

## Organización

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [service-catalog.md](./service-catalog.md) | Catálogo de microservicios y responsabilidades | 🟡 |
| [communication-patterns.md](./communication-patterns.md) | Patrones de comunicación entre servicios | 🟡 |
| [_template/](./_template/) | Plantilla para documentar nuevos servicios | 🟡 |
| [services/](./services/) | Documentación individual de cada microservicio | 🟡 |

---

## Microservicios documentados

| Servicio | Función principal |
|----------|-------------------|
| IAM Service | Autenticación, autorización y gestión de usuarios |
| Reference Data Service | Parámetros y datos institucionales |
| Academic Management Service | Programas, competencias y fichas |
| Training Environment Service | Ambientes y recursos físicos |
| Actors Service | Instructores, aprendices y empresas |
| Scheduling Service | Programación académica y horarios |
| Monitoring Service | Indicadores y monitoreo |
| Document Service | Gestión documental |
| Audit Service | Auditoría y trazabilidad |

---

## Estructura de la carpeta

```text
09-microservices/
│
├── README.md
├── service-catalog.md
├── communication-patterns.md
│
├── _template/
│   ├── README.md
│   ├── api-contract.md
│   ├── data-model.md
│   ├── events.md
│   └── responsibilities.md
│
└── services/
    ├── auth-service/
    ├── reference-data-service/
    ├── academic-management-service/
    ├── training-environment-service/
    ├── actors-service/
    ├── scheduling-service/
    ├── monitoring-service/
    ├── document-service/
    └── audit-service/
```

---

## Principios

Los microservicios implementan los siguientes principios arquitectónicos:

- Organización por dominio de negocio.
- Base de datos propia por servicio.
- Comunicación mediante APIs REST y eventos.
- Despliegue independiente.
- Bajo acoplamiento y alta cohesión.
- Escalabilidad horizontal.
- Observabilidad y auditoría desde el diseño.

---

## Relación con otras carpetas

- **02-domain:** Contextos y reglas de negocio.
- **05-architecture:** Arquitectura general del sistema.
- **06-data:** Modelos de datos compartidos.
- **07-api:** Convenciones y contratos de las APIs.
- **08-uml:** Diagramas de arquitectura y componentes.