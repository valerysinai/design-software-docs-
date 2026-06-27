# Historias de Usuario

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Propósito

Este documento reúne las principales historias de usuario del Sistema de Gestión de Horarios del SENA. Las historias representan las necesidades de los diferentes actores de la plataforma y sirven como base para la implementación de los requerimientos funcionales.

---

# Gestión de Identidad y Acceso

## HU-001 Iniciar sesión

**Como** usuario autorizado

**Quiero** acceder al sistema mediante mis credenciales

**Para** utilizar únicamente las funcionalidades permitidas según mi perfil.

### Criterios de aceptación

- Validar usuario y contraseña.
- Mostrar mensaje ante credenciales inválidas.
- Registrar el acceso exitoso.

---

## HU-002 Gestionar usuarios

**Como** administrador del sistema

**Quiero** administrar usuarios y roles

**Para** controlar el acceso a la plataforma.

### Criterios de aceptación

- Crear usuarios.
- Modificar usuarios.
- Desactivar usuarios.
- Asignar roles.

---

# Gestión Académica

## HU-003 Gestionar programas de formación

**Como** administrador académico

**Quiero** administrar programas de formación

**Para** mantener actualizada la oferta académica.

### Criterios de aceptación

- Registrar programas.
- Actualizar programas.
- Consultar programas.

---

## HU-004 Gestionar competencias y RAP

**Como** diseñador curricular

**Quiero** administrar competencias y resultados de aprendizaje

**Para** estructurar correctamente los programas de formación.

### Criterios de aceptación

- Crear competencias.
- Crear RAP.
- Asociarlos al programa.

---

## HU-005 Gestionar fichas

**Como** coordinador académico

**Quiero** crear y administrar fichas de formación

**Para** organizar la ejecución académica.

### Criterios de aceptación

- Crear fichas.
- Asociar programas.
- Consultar fichas.

---

# Gestión de Ambientes

## HU-006 Gestionar ambientes

**Como** administrador

**Quiero** registrar y actualizar ambientes

**Para** mantener disponible la infraestructura institucional.

### Criterios de aceptación

- Crear ambientes.
- Actualizar ambientes.
- Consultar ambientes.

---

# Gestión de Actores

## HU-007 Asignar instructores

**Como** coordinador académico

**Quiero** asignar instructores a las fichas

**Para** garantizar la ejecución de la formación.

### Criterios de aceptación

- Consultar disponibilidad.
- Asociar instructor.
- Validar conflictos.

---

## HU-008 Consultar horario

**Como** aprendiz

**Quiero** consultar mi horario

**Para** conocer mis actividades programadas.

### Criterios de aceptación

- Consultar horario.
- Visualizar instructor.
- Visualizar ambiente.

---

# Gestión de Horarios

## HU-009 Programar horarios

**Como** coordinador académico

**Quiero** crear horarios

**Para** organizar la programación académica.

### Criterios de aceptación

- Validar instructor.
- Validar ambiente.
- Detectar conflictos.

---

## HU-010 Aprobar programación

**Como** coordinador académico

**Quiero** aprobar los horarios generados

**Para** publicarlos oficialmente.

### Criterios de aceptación

- Revisar programación.
- Aprobar horarios.
- Registrar responsable.

---

## HU-011 Registrar incidencias

**Como** instructor

**Quiero** registrar novedades durante una sesión

**Para** mantener la trazabilidad de la ejecución.

### Criterios de aceptación

- Registrar incidencia.
- Asociarla a la sesión.
- Consultarla posteriormente.

---

# Seguimiento y Monitoreo

## HU-012 Consultar indicadores

**Como** directivo

**Quiero** visualizar indicadores de gestión

**Para** apoyar la toma de decisiones.

### Criterios de aceptación

- Consultar indicadores.
- Aplicar filtros.
- Visualizar tendencias.

---

## HU-013 Monitorear recursos

**Como** coordinador académico

**Quiero** conocer la ocupación de ambientes e instructores

**Para** optimizar la programación.

### Criterios de aceptación

- Consultar ocupación.
- Consultar disponibilidad.
- Identificar sobrecargas.

---

## HU-014 Consultar seguimiento de proyectos

**Como** directivo

**Quiero** visualizar el avance de los proyectos formativos

**Para** monitorear el cumplimiento de los objetivos.

### Criterios de aceptación

- Consultar estado.
- Visualizar avances.
- Consultar observaciones.

---

# Gestión Documental

## HU-015 Gestionar documentos

**Como** administrador académico

**Quiero** almacenar y consultar documentos

**Para** centralizar la información institucional.

### Criterios de aceptación

- Cargar documentos.
- Consultarlos.
- Gestionar versiones.

---

## HU-016 Generar reportes

**Como** directivo

**Quiero** generar reportes académicos

**Para** apoyar la toma de decisiones.

### Criterios de aceptación

- Filtrar información.
- Generar reportes.
- Exportar en PDF.

---

# Notificaciones

## HU-017 Recibir notificaciones

**Como** instructor o aprendiz

**Quiero** recibir notificaciones de cambios

**Para** mantenerme informado sobre la programación.

### Criterios de aceptación

- Notificar cambios.
- Notificar cancelaciones.
- Registrar el envío.

---

# Auditoría

## HU-018 Consultar auditoría

**Como** auditor institucional

**Quiero** consultar el historial de operaciones

**Para** verificar la trazabilidad del sistema.

### Criterios de aceptación

- Consultar eventos.
- Filtrar por usuario.
- Filtrar por fecha.

---

# Referencias

- [functional.md](./functional.md)
- [non-functional.md](./non-functional.md)
- [../03-product/product-backlog.md](../03-product/product-backlog.md)