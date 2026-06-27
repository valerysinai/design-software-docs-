# Requisitos Funcionales

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Propósito

Este documento define los requerimientos funcionales del Sistema de Gestión de Horarios del SENA.

Los requerimientos se encuentran organizados por módulos funcionales, alineados con los contextos de dominio definidos para la arquitectura del sistema.

---

# RF-01 Gestión de Identidad y Acceso

## RF-01.01 Autenticación

El sistema debe permitir el inicio y cierre de sesión mediante credenciales válidas.

## RF-01.02 Gestión de usuarios

El sistema debe permitir registrar, consultar, actualizar y desactivar usuarios.

## RF-01.03 Gestión de roles y permisos

El sistema debe permitir administrar perfiles de acceso y permisos asociados a cada usuario.

## RF-01.04 Gestión de sesiones

El sistema debe controlar la vigencia de las sesiones activas y permitir su finalización segura.

## RF-01.05 Auditoría de acceso

El sistema debe registrar los eventos relacionados con autenticación y autorización.

---

# RF-02 Información Institucional

## RF-02.01 Gestión de regionales

El sistema debe permitir administrar las regionales del SENA.

## RF-02.02 Gestión de centros de formación

El sistema debe permitir administrar los centros de formación asociados a cada regional.

## RF-02.03 Gestión de parámetros

El sistema debe permitir configurar parámetros generales utilizados por la plataforma.

## RF-02.04 Gestión de catálogos

El sistema debe administrar catálogos reutilizados por los diferentes módulos.

---

# RF-03 Gestión Académica

## RF-03.01 Gestión de programas

Administrar programas de formación.

## RF-03.02 Gestión de competencias

Administrar competencias asociadas a cada programa.

## RF-03.03 Gestión de RAP

Administrar resultados de aprendizaje.

## RF-03.04 Gestión del diseño curricular

Administrar la estructura curricular de los programas.

## RF-03.05 Gestión de fichas

Crear y administrar fichas de formación.

## RF-03.06 Gestión de proyectos formativos

Administrar proyectos formativos asociados a las fichas.

---

# RF-04 Gestión de Actores

## RF-04.01 Gestión de instructores

Administrar la información de los instructores.

## RF-04.02 Gestión de aprendices

Administrar la información de los aprendices.

## RF-04.03 Gestión de coordinadores y directivos

Administrar los usuarios responsables de la gestión académica.

---

# RF-05 Gestión de Ambientes

## RF-05.01 Gestión de ambientes

Registrar y administrar ambientes de formación.

## RF-05.02 Gestión de recursos

Administrar el inventario de recursos disponibles en cada ambiente.

## RF-05.03 Disponibilidad de ambientes

Controlar la disponibilidad de los ambientes para la programación académica.

## RF-05.04 Gestión de mantenimiento

Registrar periodos de mantenimiento o indisponibilidad de los ambientes.

---

# RF-06 Gestión de Horarios

## RF-06.01 Programación de horarios

Crear, consultar, actualizar y cancelar horarios académicos.

## RF-06.02 Asignación de instructores

Asignar instructores a las sesiones programadas.

## RF-06.03 Asignación de ambientes

Asignar ambientes disponibles a cada sesión.

## RF-06.04 Validación de restricciones

Validar disponibilidad de instructores, ambientes y franjas horarias antes de confirmar una programación.

## RF-06.05 Detección de conflictos

Detectar conflictos de programación antes de registrar un horario.

## RF-06.06 Reprogramación

Permitir modificar horarios existentes manteniendo la trazabilidad de los cambios.

---

# RF-07 Seguimiento y Monitoreo

## RF-07.01 Gestión de indicadores

Calcular indicadores relacionados con la programación académica.

## RF-07.02 Gestión de alertas

Generar alertas cuando se detecten situaciones que requieran atención.

## RF-07.03 Notificaciones

Enviar notificaciones a los usuarios involucrados en eventos relevantes.

## RF-07.04 Dashboard

Mostrar información consolidada mediante tableros de control.

---

# RF-08 Gestión Documental

## RF-08.01 Generación de documentos

Generar automáticamente documentos asociados a los procesos académicos.

## RF-08.02 Gestión de plantillas

Administrar las plantillas utilizadas para la generación de documentos.

## RF-08.03 Exportación de información

Permitir la exportación de reportes en formato PDF.

---

# RF-09 Auditoría y Trazabilidad

## RF-09.01 Registro de auditoría

Registrar todas las operaciones relevantes realizadas en la plataforma.

## RF-09.02 Consulta de auditoría

Permitir consultar el historial de cambios realizados sobre las entidades del sistema.

## RF-09.03 Trazabilidad de eventos

Mantener la trazabilidad de las operaciones ejecutadas entre los diferentes módulos.

---

# Referencias

- [../02-domain/domain-map.md](../02-domain/domain-map.md)
- [../02-domain/entities/](../02-domain/entities/)
- [../03-product/product-backlog.md](../03-product/product-backlog.md)
- [non-functional.md](./non-functional.md)
- [user-stories.md](./user-stories.md)