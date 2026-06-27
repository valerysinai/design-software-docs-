# Contrato de API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Endpoints principales

| Método | Endpoint | Descripción |
|---------|----------|-------------|
| GET | /ambientes | Consultar ambientes |
| POST | /ambientes | Registrar ambiente |
| PUT | /ambientes/{id} | Actualizar ambiente |
| GET | /inventario | Consultar inventario |
| POST | /inventario | Registrar recurso |
| GET | /disponibilidad | Consultar disponibilidad |

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