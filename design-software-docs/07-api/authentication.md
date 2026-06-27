# Autenticación y autorización

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Definir el mecanismo de autenticación y autorización utilizado por las APIs del sistema **Gestión de Horarios SENA**, garantizando el acceso seguro a los recursos y la protección de la información.

---

# Arquitectura de autenticación

La plataforma utiliza un esquema de autenticación basado en **JWT (JSON Web Token)** administrado por el **IAM Service**.

El proceso de autenticación sigue el siguiente flujo:

```text
Usuario
      │
      ▼
Inicio de sesión
      │
      ▼
IAM Service
      │
Genera JWT
      │
      ▼
API Gateway
      │
Valida el token
      │
      ▼
Microservicio solicitado