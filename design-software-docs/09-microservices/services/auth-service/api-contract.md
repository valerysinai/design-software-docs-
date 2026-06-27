# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| POST | /auth/login | Iniciar sesión |
| POST | /auth/logout | Cerrar sesión |
| POST | /auth/refresh | Renovar token |
| GET | /users | Consultar usuarios |
| POST | /users | Crear usuario |
| PUT | /users/{id} | Actualizar usuario |
| DELETE | /users/{id} | Desactivar usuario |
| GET | /roles | Consultar roles |

---

## Seguridad

- Autenticación mediante JWT.
- Autorización basada en roles (RBAC).
- Comunicación mediante HTTPS.

---

## Respuestas

| Código | Significado |
|---------|-------------|
| 200 | Operación exitosa |
| 201 | Recurso creado |
| 400 | Solicitud inválida |
| 401 | No autenticado |
| 403 | Acceso denegado |
| 404 | Recurso no encontrado |
| 500 | Error interno |