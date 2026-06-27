# Gestión de Identidad y Acceso
> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Administrar la autenticación, autorización y control de acceso de los usuarios que interactúan con la plataforma.

---

## Usuario

Representa una persona autorizada para utilizar el sistema.

### Atributos principales

- Identificador
- Nombre completo
- Correo electrónico
- Estado
- Fecha del último acceso

### Relaciones

- Tiene uno o varios roles.
- Puede iniciar múltiples sesiones.
- Sus acciones son registradas en auditoría.

### Restricciones

- El correo electrónico debe ser único.
- Solo usuarios activos pueden autenticarse.
- Las credenciales deben almacenarse mediante mecanismos seguros.

---

## Rol

Define el conjunto de permisos asignados a un usuario.

### Atributos principales

- Nombre
- Descripción
- Permisos

### Roles del sistema

- Administrador
- Director
- Coordinador
- Instructor
- Aprendiz

### Restricciones

- Un usuario puede tener uno o varios roles.
- Solo administradores pueden modificar permisos.

---

## Sesión

Representa una conexión autenticada dentro de la plataforma.

### Atributos principales

- Token
- Usuario
- Fecha de inicio
- Fecha de expiración
- Dirección IP

### Restricciones

- Toda sesión posee tiempo de expiración.
- Las sesiones expiradas deben invalidarse automáticamente.

---

## Reglas del contexto

- Solo usuarios autenticados pueden acceder a funcionalidades protegidas.
- Todas las operaciones deben ejecutarse bajo un usuario identificado.
- Los permisos determinan las acciones disponibles para cada rol.