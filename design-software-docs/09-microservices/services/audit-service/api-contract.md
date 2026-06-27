# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /auditoria | Consultar registros |
| GET | /auditoria/{id} | Consultar registro específico |
| POST | /auditoria | Registrar evento |
| GET | /auditoria/exportar | Exportar registros |

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
| 201 | Registro creado |
| 400 | Solicitud inválida |
| 401 | No autorizado |
| 404 | Registro no encontrado |
| 500 | Error interno |