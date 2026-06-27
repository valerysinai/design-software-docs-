# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Registro de Auditoría

- id
- usuario
- servicio
- operación
- recurso
- fechaHora
- resultado

### Evento

- id
- tipo
- descripción
- origen
- fechaHora

---

## Relaciones

- Un registro de auditoría puede estar asociado a uno o varios eventos.
- Cada evento corresponde a una operación realizada por un microservicio.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.