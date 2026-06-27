# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /documentos | Consultar documentos |
| POST | /documentos | Registrar documento |
| GET | /documentos/{id} | Consultar documento |
| PUT | /documentos/{id} | Actualizar documento |
| GET | /documentos/{id}/descargar | Descargar documento |

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
| 404 | Documento no encontrado |
| 500 | Error interno |