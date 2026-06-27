# Contratos OpenAPI

> Estado: 🔴 Pendiente | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Esta carpeta almacenará los contratos **OpenAPI 3.x** oficiales de los microservicios del sistema Gestión de Horarios SENA.

Los archivos aquí publicados representan la versión aprobada por el equipo de arquitectura y son la referencia para consumidores internos y externos.

---

## Organización

Cada microservicio tendrá un archivo independiente.

Ejemplo:

```text
contracts/
└── openapi/
    ├── auth-service.yaml
    ├── scheduling-service.yaml
    ├── academic-service.yaml
    ├── actors-service.yaml
    ├── environment-service.yaml
    ├── reference-data-service.yaml
    ├── monitoring-service.yaml
    ├── document-service.yaml
    └── audit-service.yaml
```

---

## Convenciones

Todos los contratos deberán cumplir con:

- OpenAPI 3.x.
- Versionado mediante `/api/v1`.
- Esquemas JSON consistentes.
- Códigos HTTP estandarizados.
- Seguridad mediante JWT.
- Documentación completa de parámetros y respuestas.

---

## Relación con el proyecto

Durante el desarrollo, cada microservicio mantiene su contrato de trabajo en:

```text
09-microservices/services/<service>/api-contract.md
```

Cuando el contrato sea aprobado, se publicará en esta carpeta como un archivo `.yaml`.

---

## Estado actual

Los contratos OpenAPI serán incorporados a medida que los microservicios alcancen una versión estable.