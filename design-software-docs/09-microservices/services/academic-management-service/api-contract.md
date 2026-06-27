# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /programas | Consultar programas |
| POST | /programas | Crear programa |
| GET | /competencias | Consultar competencias |
| POST | /competencias | Crear competencia |
| GET | /rap | Consultar resultados de aprendizaje |
| GET | /fichas | Consultar fichas |
| POST | /fichas | Crear ficha |

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
| 404 | No encontrado |
| 500 | Error interno |