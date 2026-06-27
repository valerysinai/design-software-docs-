# Eventos del servicio

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Eventos publicados

| Evento | Descripción |
|---------|-------------|
| EnvironmentCreated | Ambiente registrado |
| EnvironmentUpdated | Ambiente actualizado |
| EnvironmentBlocked | Ambiente bloqueado por mantenimiento |
| EnvironmentAvailable | Ambiente disponible nuevamente |

---

## Eventos consumidos

El servicio recibe solicitudes para consultar disponibilidad y recursos de los ambientes de formación.

---

## Servicios consumidores

- Scheduling Service
- Monitoring Service
- Audit Service

---

## Objetivo

Mantener actualizada la información de los ambientes y garantizar que su disponibilidad pueda ser consultada por los demás microservicios.