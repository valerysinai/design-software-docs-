# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Usuario

- id
- nombre
- correo
- contraseña
- estado

### Rol

- id
- nombre
- descripción

### Permiso

- id
- nombre
- recurso

### Sesión

- id
- usuarioId
- token
- fechaInicio
- fechaExpiración

---

## Relaciones

- Un usuario puede tener uno o varios roles.
- Un rol puede contener múltiples permisos.
- Un usuario puede tener varias sesiones activas según la configuración del sistema.

---

## Persistencia

El servicio administra una base de datos independiente siguiendo el patrón **Database per Service**.