# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Programa

- id
- código
- nombre
- duración

### Competencia

- id
- nombre
- descripción

### Resultado de Aprendizaje (RAP)

- id
- nombre
- competenciaId

### Ficha

- id
- código
- programaId
- jornada
- estado

---

## Relaciones

- Un programa contiene varias competencias.
- Una competencia contiene varios resultados de aprendizaje.
- Una ficha pertenece a un programa.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.