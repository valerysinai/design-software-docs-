# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /regionales | Consultar regionales |
| POST | /regionales | Crear regional |
| GET | /centros | Consultar centros |
| POST | /centros | Crear centro |
| GET | /catalogos | Consultar catálogos |
| GET | /parametros | Consultar parámetros |
| PUT | /parametros/{id} | Actualizar parámetro |

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
| 201 | Creado |
| 400 | Solicitud inválida |
| 401 | No autorizado |
| 404 | No encontrado |
| 500 | Error interno |