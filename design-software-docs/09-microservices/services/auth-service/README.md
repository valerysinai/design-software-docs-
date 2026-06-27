# IAM Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **IAM Service** (Identity and Access Management) es responsable de la autenticación, autorización y administración de usuarios dentro de la plataforma Gestión de Horarios SENA.

Este servicio centraliza el control de acceso y garantiza que únicamente los usuarios autorizados puedan utilizar los diferentes módulos del sistema.

---

## Responsabilidades

- Gestionar usuarios.
- Administrar roles y permisos.
- Autenticar usuarios.
- Gestionar sesiones.
- Emitir y validar tokens JWT.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [responsibilities.md](./responsibilities.md) | Funciones y alcance del servicio | 🟡 |
| [api-contract.md](./api-contract.md) | Endpoints y contratos de la API | 🟡 |
| [data-model.md](./data-model.md) | Modelo de datos del servicio | 🟡 |
| [events.md](./events.md) | Eventos publicados y consumidos | 🟡 |

---

## Dependencias

El servicio se comunica principalmente con:

- API Gateway
- Audit Service
- Monitoring Service

---

## Base de datos

El IAM Service administra una base de datos propia donde almacena:

- Usuarios
- Roles
- Permisos
- Sesiones
- Tokens (cuando aplique)

---

## Principios

- Base de datos independiente.
- Autenticación mediante JWT.
- Control de acceso basado en roles (RBAC).
- Comunicación mediante APIs REST y eventos.