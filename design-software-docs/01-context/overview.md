# Descripción general del proyecto

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

## Contexto institucional

El **Servicio Nacional de Aprendizaje (SENA)** es una entidad pública colombiana encargada de la formación profesional integral mediante programas técnicos, tecnológicos y de formación complementaria. Entre estos programas se encuentra **ADSO (Análisis y Desarrollo de Software)**, cuya formación se estructura en competencias, Resultados de Aprendizaje (RAP), proyectos formativos y procesos de seguimiento académico.

Cada programa de formación se organiza en **fichas**, las cuales agrupan aprendices, instructores, ambientes de formación, horarios y recursos necesarios para el desarrollo de las actividades académicas. La planificación y administración de estos elementos constituye un proceso crítico para garantizar el adecuado desarrollo de la formación.

Actualmente, gran parte de la asignación y gestión de horarios se realiza mediante procesos manuales, lo que incrementa la probabilidad de inconsistencias, dificulta la coordinación entre las diferentes áreas académicas y limita la capacidad de seguimiento sobre la ejecución de la formación.

El **Sistema de Gestión de Horarios del SENA** surge como una plataforma orientada a centralizar y automatizar estos procesos, proporcionando mecanismos para la planificación académica, la asignación de horarios, el seguimiento de la ejecución formativa y la trazabilidad de la información. El sistema complementa las plataformas institucionales existentes, como **SOFIA Plus**, mediante procesos de sincronización de información, sin reemplazar sus funciones administrativas.

## Problema

La gestión manual de horarios y recursos académicos presenta diversas dificultades operativas que afectan la eficiencia del proceso formativo, entre ellas:

* **Conflictos de asignación:** instructores, ambientes o fichas programados simultáneamente en diferentes actividades.
* **Falta de visibilidad:** ausencia de información consolidada sobre ocupación de ambientes, disponibilidad de instructores y carga académica.
* **Ineficiencia operativa:** procesos repetitivos que demandan un alto esfuerzo administrativo.
* **Dificultad para gestionar cambios:** modificaciones de horarios que generan inconsistencias al no propagarse automáticamente.
* **Ausencia de alertas y validaciones:** inexistencia de mecanismos que detecten conflictos antes de confirmar una programación.
* **Limitaciones para el análisis institucional:** dificultad para generar indicadores que apoyen la toma de decisiones relacionadas con utilización de recursos y desempeño académico.

## Objetivos

### Objetivo general

Desarrollar una plataforma modular, escalable y auditable que permita automatizar y centralizar la gestión de horarios del SENA, garantizando la trazabilidad de la ejecución formativa y optimizando la administración de recursos académicos.

### Objetivos específicos

1. Automatizar la asignación de horarios mediante validaciones que eviten conflictos entre instructores, ambientes y fichas de formación.
2. Implementar un motor de programación que considere restricciones de disponibilidad, capacidad y competencias.
3. Registrar la trazabilidad de las sesiones de formación, asistencia, novedades e incidencias durante el proceso académico.
4. Facilitar el seguimiento del avance de fichas y aprendices mediante información actualizada en tiempo real.
5. Gestionar la relación entre programas de formación, diseños curriculares, competencias, RAP, proyectos formativos y evidencias.
6. Generar reportes, actas y documentos que respalden los procesos administrativos y académicos.
7. Proporcionar tableros de control que apoyen la toma de decisiones por parte de coordinadores, instructores y personal administrativo.

## Actores principales

El sistema está dirigido a los siguientes actores institucionales:

* Administradores del sistema.
* Coordinadores académicos.
* Instructores.
* Aprendices.
* Personal administrativo responsable de la programación académica.

## Beneficios esperados

La implementación del sistema permitirá:

* Reducir conflictos en la programación de horarios.
* Optimizar la utilización de ambientes y recursos institucionales.
* Disminuir el tiempo requerido para realizar la programación académica.
* Mejorar la trazabilidad de la ejecución de la formación.
* Facilitar el seguimiento del avance de aprendices y fichas.
* Proporcionar información confiable para la generación de indicadores y la toma de decisiones.
* Centralizar la gestión de horarios en una plataforma integrada y escalable.

## Alineación normativa

El desarrollo del sistema considera como marco de referencia la normativa y documentación institucional aplicable, entre la que se destacan:

* Acuerdo 009 de 2024 (creación del programa ADSO).
* Ley 119 de 1994, que establece la naturaleza, misión y funciones del SENA.
* Manual de Diseño Curricular del SENA.
* Ley 1581 de 2012 y Decreto 1377 de 2013 sobre protección de datos personales.
* Ley 594 de 2000 sobre gestión documental.

Estas disposiciones sirven como referencia para el diseño funcional y el manejo de la información dentro del sistema.

## Referencias

* [01-context/scope.md](./scope.md) — Alcance funcional y exclusiones del proyecto.
* [01-context/glossary.md](./glossary.md) — Definiciones de términos del dominio.
* [04-requirements/functional.md](../04-requirements/functional.md) — Requerimientos funcionales.
* [05-architecture/overview.md](../05-architecture/overview.md) — Descripción de la arquitectura del sistema.
* [15-project-control/open-questions.md](../15-project-control/open-questions.md) — Preguntas abiertas y decisiones pendientes.
