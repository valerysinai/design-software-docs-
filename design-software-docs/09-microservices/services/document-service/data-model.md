# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Documento

- id
- nombre
- tipo
- ruta
- fechaCreacion
- estado

### Versión

- id
- documentoId
- número
- fecha
- autor

---

## Relaciones

- Un documento puede tener varias versiones.
- Cada versión pertenece a un único documento.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.