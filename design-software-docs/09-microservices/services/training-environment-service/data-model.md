# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Ambiente

- id
- nombre
- tipo
- capacidad
- estado
- centroId

### Recurso

- id
- nombre
- tipo
- cantidad
- ambienteId

### Disponibilidad

- id
- ambienteId
- fecha
- horaInicio
- horaFin
- estado

---

## Relaciones

- Un ambiente puede contener varios recursos.
- Un ambiente puede tener múltiples registros de disponibilidad.
- Cada recurso pertenece a un ambiente.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.