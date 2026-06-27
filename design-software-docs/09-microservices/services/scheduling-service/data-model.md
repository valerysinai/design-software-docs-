# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Horario

- id
- fichaId
- instructorId
- ambienteId
- fecha
- horaInicio
- horaFin
- estado

### Sesión

- id
- horarioId
- tema
- observaciones

### Incidencia

- id
- horarioId
- descripción
- fecha
- estado

### Conflicto

- id
- tipo
- recursoAfectado
- descripción

---

## Relaciones

- Un horario puede contener varias sesiones.
- Una sesión pertenece a un horario.
- Un horario puede registrar múltiples incidencias.
- Los conflictos están asociados a un horario o recurso.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.