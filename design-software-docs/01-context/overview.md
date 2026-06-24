# Descripción general del proyecto

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Arquitectura / Gestión

## Contexto institucional

El Servicio Nacional de Aprendizaje (SENA) es una institución pública colombiana que forma trabajadores en programas técnicos y tecnológicos. El programa ADSO (Análisis y Desarrollo de Sistemas de Información) es un programa de formación técnica con duración aproximada de 2 años, estructurado en competencias y Resultados de Aprendizaje Específicos (RAPs).

Cada programa se materializa en **fichas de formación** que agrupan instructores, aprendices, ambientes (aulas, laboratorios), recursos y horarios. La asignación manual de horarios es un proceso complejo, propenso a errores y costoso en tiempo administrativo.

La plataforma **Horarios SENA** no reemplaza a SOFIA Plus. Su alcance es la trazabilidad de la ejecución formativa: qué estaba programado, qué se ejecutó realmente, qué evidencias se entregaron y qué avance tiene cada aprendiz. La integración con fuentes maestras institucionales se hace mediante sincronización, no sustitución.

## Problema

Actualmente la asignación de horarios en el SENA se realiza de forma manual sin herramientas especializadas. Esto genera:

- **Conflictos de asignación:** instructores o ambientes asignados simultáneamente a múltiples fichas.
- **Falta de visibilidad:** direcciones administrativas sin datos consolidados de ocupación y disponibilidad.
- **Ineficiencia operativa:** procesos repetitivos sin automatización.
- **Dificultad en ajustes:** cambios que no se propagan automáticamente y generan inconsistencias.
- **Ausencia de alertas:** sin notificaciones ante cambios o conflictos.
- **Limitaciones analíticas:** imposibilidad de medir KPIs sobre utilización de ambientes y carga de instructores.

## Objetivos

**Objetivo general:** Construir una plataforma modular, auditable y extensible que automatice y centralice la asignación y gestión de horarios de fichas de formación del SENA, con trazabilidad verificable de la ejecución formativa.

**Objetivos específicos:**

1. Eliminar conflictos de asignación mediante validación automática en tiempo real.
2. Proveer un motor de asignación que respete restricciones de capacidad, disponibilidad y competencias.
3. Registrar trazabilidad precisa de sesiones, asistencia, novedades e incidencias.
4. Gestionar avance de fichas y aprendices con visibilidad en tiempo real.
5. Relacionar proyectos formativos con programas, diseño curricular, competencias, RAPs, evidencias y entregables.
6. Generar reportes, actas y documentos PDF con trazabilidad documental.
7. Proveer tablero de control para coordinadores, directivos e instructores.

## Alineación normativa

- Acuerdo 009 de 2024 (creación del programa ADSO)
- Ley 119 de 1994: naturaleza, misión y funciones del SENA
- Manual de Diseño Curricular SENA
- Ley 1581 de 2012 y Decreto 1377 de 2013 sobre protección de datos personales
- Ley 594 de 2000 sobre gestión documental

> Toda regla institucional debe quedar trazada a fuente normativa o decisión explícita del product owner. No se inventan reglas internas SENA no entregadas como fuente.

## Referencias

- [01-context/scope.md](./scope.md) — Alcance detallado y exclusiones
- [01-context/glossary.md](./glossary.md) — Glosario del dominio
- [04-requirements/functional.md](../04-requirements/functional.md) — Requerimientos funcionales
- [05-architecture/overview.md](../05-architecture/overview.md) — Vista arquitectónica
- [15-project-control/open-questions.md](../15-project-control/open-questions.md) — Preguntas abiertas