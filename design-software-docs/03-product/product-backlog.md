# Backlog del producto

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Propósito

Este documento presenta las principales funcionalidades del Sistema de Gestión de Horarios del SENA organizadas por **épicas**. Cada épica agrupa capacidades relacionadas que aportan valor al producto y sirven como base para la definición de los requerimientos funcionales.

---

# Priorización

| Prioridad | Descripción |
|-----------|-------------|
| Alta | Funcionalidades indispensables para el funcionamiento del sistema (MVP). |
| Media | Funcionalidades que amplían las capacidades del sistema. |
| Baja | Mejoras y funcionalidades futuras. |

---

# Épicas del producto

## EP-01 Gestión de usuarios y seguridad

**Prioridad:** Alta

**Objetivo**

Administrar la autenticación, autorización y control de acceso de los usuarios.

**Funcionalidades principales**

- Inicio de sesión.
- Administración de usuarios.
- Gestión de roles y permisos.
- Recuperación de credenciales.
- Gestión de sesiones.

---

## EP-02 Gestión institucional

**Prioridad:** Alta

**Objetivo**

Administrar la estructura institucional utilizada por el sistema.

**Funcionalidades principales**

- Gestión de regionales.
- Gestión de centros de formación.
- Administración de parámetros.
- Gestión de catálogos.

---

## EP-03 Gestión académica

**Prioridad:** Alta

**Objetivo**

Administrar la información académica utilizada durante la programación.

**Funcionalidades principales**

- Gestión de programas de formación.
- Gestión de competencias.
- Gestión de RAP.
- Administración de fichas.
- Organización de jornadas.

---

## EP-04 Gestión de actores

**Prioridad:** Alta

**Objetivo**

Administrar instructores, aprendices y demás actores involucrados.

**Funcionalidades principales**

- Registro de instructores.
- Administración de aprendices.
- Gestión de disponibilidad.
- Gestión de empresas para etapa productiva.

---

## EP-05 Gestión de ambientes

**Prioridad:** Alta

**Objetivo**

Administrar los espacios físicos donde se desarrolla la formación.

**Funcionalidades principales**

- Registro de ambientes.
- Administración de recursos.
- Gestión de disponibilidad.
- Control de mantenimiento.

---

## EP-06 Gestión de horarios

**Prioridad:** Alta

**Objetivo**

Planificar y administrar la programación académica.

**Funcionalidades principales**

- Creación de horarios.
- Validación de restricciones.
- Asignación de instructores.
- Asignación de ambientes.
- Gestión de conflictos.
- Reprogramación de sesiones.

---

## EP-07 Motor de asignación

**Prioridad:** Alta

**Objetivo**

Automatizar la generación de horarios respetando las reglas del negocio.

**Funcionalidades principales**

- Generación automática de horarios.
- Validación de disponibilidad.
- Optimización de recursos.
- Detección de conflictos.

---

## EP-08 Seguimiento y monitoreo

**Prioridad:** Media

**Objetivo**

Proporcionar información sobre el comportamiento operativo del sistema.

**Funcionalidades principales**

- Indicadores de gestión.
- Alertas operativas.
- Tableros de control.
- Seguimiento de ejecución.

---

## EP-09 Gestión documental

**Prioridad:** Media

**Objetivo**

Generar y administrar documentos producidos por la plataforma.

**Funcionalidades principales**

- Generación de reportes.
- Actas.
- Certificados.
- Exportación a PDF.

---

## EP-10 Auditoría y trazabilidad

**Prioridad:** Alta

**Objetivo**

Registrar todas las operaciones relevantes realizadas en la plataforma.

**Funcionalidades principales**

- Auditoría de operaciones.
- Historial de cambios.
- Registro de eventos.
- Consulta de trazabilidad.

---

# Resumen de prioridades

| Épica | Prioridad |
|--------|-----------|
| Gestión de usuarios y seguridad | Alta |
| Gestión institucional | Alta |
| Gestión académica | Alta |
| Gestión de actores | Alta |
| Gestión de ambientes | Alta |
| Gestión de horarios | Alta |
| Motor de asignación | Alta |
| Seguimiento y monitoreo | Media |
| Gestión documental | Media |
| Auditoría y trazabilidad | Alta |

---

# Relación con otras carpetas

Este backlog sirve como punto de partida para:

- La especificación de requerimientos funcionales (`04-requirements`).
- La definición de los módulos de la arquitectura (`05-architecture`).
- La planificación de versiones del producto (`roadmap.md`).

---

# Referencias

- [vision.md](./vision.md)
- [roadmap.md](./roadmap.md)
- [../04-requirements/functional.md](../04-requirements/functional.md)