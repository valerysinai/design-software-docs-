# Eventos del servicio

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Eventos publicados

| Evento | Descripción |
|---------|-------------|
| ScheduleCreated | Horario creado |
| ScheduleUpdated | Horario actualizado |
| ScheduleCancelled | Horario cancelado |
| ConflictDetected | Conflicto de programación detectado |
| IncidentReported | Incidencia registrada |

---

## Eventos consumidos

El servicio consume información de programas, instructores, ambientes y parámetros institucionales para validar la programación académica.

---

## Servicios consumidores

- Monitoring Service
- Audit Service
- Document Service

---

## Objetivo

Mantener sincronizada la programación académica y notificar los cambios relevantes a los demás microservicios mediante eventos.