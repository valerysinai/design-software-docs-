# Requisitos Funcionales

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Por definir

## RF-01 Seguridad y Acceso

### RF-01.01 Gestión de autenticación

El sistema debe permitir el inicio y cierre de sesión mediante credenciales válidas.

### RF-01.02 Gestión de usuarios

El sistema debe permitir crear, actualizar, consultar y desactivar usuarios.

### RF-01.03 Gestión de roles y permisos

El sistema debe permitir administrar perfiles de acceso y permisos asociados.

### RF-01.04 Multi-tenant

El sistema debe garantizar el aislamiento lógico de la información según la estructura institucional correspondiente.

### RF-01.05 Auditoría

El sistema debe registrar las acciones realizadas por los usuarios sobre los recursos del sistema.

---

## RF-02 Estructura Institucional

### RF-02.01 Gestión de regionales

Administrar regionales del SENA.

### RF-02.02 Gestión de centros de formación

Administrar centros de formación asociados a cada regional.

### RF-02.03 Gestión de ubicaciones

Registrar y consultar ubicaciones físicas asociadas a centros y ambientes.

---

## RF-03 Infraestructura y Ambientes

### RF-03.01 Gestión de ambientes

Registrar y administrar ambientes de formación.

### RF-03.02 Gestión de inventario

Administrar recursos físicos asociados a cada ambiente.

### RF-03.03 Disponibilidad de ambientes

Controlar la disponibilidad de ambientes para programación académica.

---

## RF-04 Parametrización

### RF-04.01 Catálogos base

Administrar catálogos reutilizados por los diferentes módulos.

### RF-04.02 Parámetros generales

Configurar parámetros operativos del sistema.

---

## RF-05 Programas de Formación

### RF-05.01 Gestión de programas

Administrar programas de formación.

### RF-05.02 Tipos de formación

Administrar modalidades y tipos de formación.

### RF-05.03 Líneas tecnológicas

Gestionar líneas tecnológicas institucionales.

### RF-05.04 Diseño curricular

Administrar competencias y estructuras curriculares.

### RF-05.05 Gestión de RAP

Administrar resultados de aprendizaje asociados a competencias.

---

## RF-06 Oferta y Programas

### RF-06.01 Gestión de proyectos formativos

Administrar proyectos formativos.

### RF-06.02 Gestión de fichas

Crear y administrar fichas de formación.

### RF-06.03 Asociación de aprendices

Permitir la asignación de aprendices a fichas.

### RF-06.04 Gestión de entregables

Administrar entregables asociados a proyectos formativos.

---

## RF-07 Actores

### RF-07.01 Gestión de instructores

Administrar información de instructores.

### RF-07.02 Gestión de aprendices

Administrar información de aprendices.

### RF-07.03 Gestión de directivos

Administrar información de directivos.

---

## RF-08 Horarios

### RF-08.01 Programación de horarios

Crear y administrar horarios académicos.

### RF-08.02 Asignación de instructores

Asignar instructores a sesiones de formación.

### RF-08.03 Asignación de ambientes

Asignar ambientes disponibles a las sesiones programadas.

### RF-08.04 Gestión de observaciones

Registrar observaciones relacionadas con la programación.

### RF-08.05 Gestión de incidencias

Registrar y consultar incidencias académicas.

### RF-08.06 Detección de conflictos

Identificar conflictos de programación antes de confirmar horarios.

---

## RF-09 Proyectos Formativos

### RF-09.01 Seguimiento

Realizar seguimiento al avance de proyectos formativos.

### RF-09.02 Notificaciones

Generar notificaciones asociadas a eventos relevantes del proyecto.

---

# RF-10 Reportes

## RF-10.01 Reportes académicos

El sistema deberá generar reportes de programación académica filtrados por centro de formación, programa, ficha, instructor y ambiente.

## RF-10.02 Exportación de información

El sistema deberá permitir exportar reportes en formatos PDF y Excel.

## RF-10.03 Indicadores operativos

El sistema deberá mostrar indicadores relacionados con ocupación de ambientes, carga de instructores y ejecución de horarios.

---

# RF-11 Notificaciones

## RF-11.01 Notificaciones automáticas

El sistema deberá enviar notificaciones cuando se creen, modifiquen o cancelen horarios.

## RF-11.02 Alertas de conflicto

El sistema deberá informar automáticamente la detección de conflictos de programación.

## RF-11.03 Recordatorios

El sistema deberá generar recordatorios de actividades programadas para instructores y aprendices.

---

# RF-12 Gestión Documental

## RF-12.01 Administración de plantillas

El sistema deberá permitir gestionar plantillas institucionales asociadas a procesos académicos.

## RF-12.02 Control de versiones

El sistema deberá mantener un historial de versiones de los documentos almacenados.

## RF-12.03 Consulta documental

El sistema deberá permitir la búsqueda y consulta de documentos asociados a programas, fichas y ambientes.

---

# RF-13 Auditoría y Monitoreo

## RF-13.01 Registro de eventos

El sistema deberá registrar eventos críticos realizados por los usuarios.

## RF-13.02 Consulta de auditoría

El sistema deberá permitir consultar la trazabilidad de las acciones ejecutadas.

## RF-13.03 Métricas operativas

El sistema deberá recopilar y visualizar métricas de desempeño y utilización de los servicios.

