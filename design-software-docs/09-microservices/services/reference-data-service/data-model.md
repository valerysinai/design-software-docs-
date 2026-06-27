# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Regional

- id
- nombre
- ubicación

### Centro de Formación

- id
- nombre
- regionalId
- dirección

### Catálogo

- id
- tipo
- valor

### Parámetro

- id
- clave
- valor
- descripción

---

## Relaciones

- Una regional puede tener varios centros.
- Los parámetros pueden ser consultados por todos los servicios autorizados.
- Los catálogos son compartidos entre diferentes módulos.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.