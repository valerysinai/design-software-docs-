# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-26

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /horarios | Consultar horarios |
| POST | /horarios | Crear horario |
| PUT | /horarios/{id} | Actualizar horario |
| DELETE | /horarios/{id} | Cancelar horario |
| GET | /conflictos | Consultar conflictos |
| POST | /incidencias | Registrar incidencia |

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