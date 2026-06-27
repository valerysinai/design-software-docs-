# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Instructor

- id
- nombre
- documento
- especialidad
- disponibilidad
- estado

### Aprendiz

- id
- nombre
- documento
- fichaId
- estado

### Coordinador

- id
- nombre
- correo
- centroId

### Directivo

- id
- nombre
- cargo
- centroId

---

## Relaciones

- Un instructor puede estar asignado a varias fichas.
- Un aprendiz pertenece a una ficha de formación.
- Coordinadores y directivos están asociados a un centro de formación.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.