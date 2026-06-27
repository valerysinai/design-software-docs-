# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /instructores | Consultar instructores |
| POST | /instructores | Registrar instructor |
| PUT | /instructores/{id} | Actualizar instructor |
| GET | /aprendices | Consultar aprendices |
| POST | /aprendices | Registrar aprendiz |
| GET | /coordinadores | Consultar coordinadores |
| GET | /directivos | Consultar directivos |

---

## Seguridad

- JWT.
- HTTPS.
- RBAC.

---

## Respuestas

| Código | Significado |
|---------|-------------|
| 200 | Correcto |
| 201 | Recurso creado |
| 400 | Solicitud inválida |
| 401 | No autorizado |
| 404 | Recurso no encontrado |
| 500 | Error interno |