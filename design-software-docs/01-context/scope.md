# Alcance del proyecto

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

## Propósito

Este documento define el alcance funcional del **Sistema de Gestión de Horarios del SENA**, especificando las funcionalidades incluidas, las exclusiones del proyecto, así como los supuestos y restricciones bajo los cuales será desarrollado e implementado.

---

# En alcance

El sistema contempla las siguientes funcionalidades:

1. Gestionar la programación de horarios para fichas de formación, instructores y ambientes.
2. Registrar la ejecución real de las sesiones de formación, incluyendo asistencia, novedades e incidencias.
3. Realizar seguimiento al avance de fichas y aprendices durante el proceso formativo.
4. Administrar la relación entre programas de formación, diseños curriculares, competencias, resultados de aprendizaje (RAP), proyectos formativos y evidencias.
5. Gestionar proyectos formativos y sus dependencias.
6. Detectar automáticamente conflictos de programación entre instructores, ambientes y horarios.
7. Automatizar la asignación de horarios considerando restricciones de disponibilidad, capacidad y reglas del negocio.
8. Generar reportes, actas y documentos institucionales.
9. Enviar notificaciones y alertas relacionadas con cambios, conflictos y eventos relevantes.
10. Proporcionar indicadores (KPIs) y tableros de seguimiento para apoyar la toma de decisiones.
11. Gestionar información de referencia como centros de formación, regionales, jornadas, ambientes y parámetros del sistema.
12. Mantener trazabilidad de las operaciones realizadas sobre la programación académica.
13. Integrarse con sistemas institucionales mediante procesos de sincronización de información.

---

# Fuera de alcance

El proyecto no contempla las siguientes funcionalidades:

1. Reemplazar las funciones administrativas de **SOFIA Plus** ni convertirse en la fuente maestra de información institucional.
2. Gestionar procesos de nómina, contratación o administración laboral de instructores.
3. Administrar calificaciones o procesos oficiales de evaluación académica.
4. Implementar una plataforma de aprendizaje virtual (LMS).
5. Gestionar sistemas biométricos de control de asistencia.
6. Integrarse con plataformas financieras, contables o presupuestales.
7. Administrar eventos externos ajenos al proceso académico del SENA.
8. Desarrollar integraciones específicas con software propietario de terceros que no formen parte de los requerimientos del proyecto.
9. Sustituir los procesos oficiales de administración curricular definidos por la institución.

---

# Supuestos

Para el correcto funcionamiento del sistema se asume que:

* Los instructores, ambientes, fichas y programas de formación existen previamente en las fuentes institucionales correspondientes.
* La programación académica sigue el calendario oficial definido por el SENA.
* Los usuarios cuentan con acceso a navegadores web modernos y conexión estable a la red.
* La información sincronizada desde los sistemas institucionales es confiable y se encuentra previamente validada.
* La infraestructura tecnológica disponible soporta la ejecución de los procesos de programación y consulta en tiempo real.

---

# Restricciones

| Tipo           | Restricción                                                                                                                                                     |
| -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Regulatoria    | Cumplimiento de la normativa institucional del SENA y de la legislación colombiana aplicable en materia de protección de datos personales y gestión documental. |
| Operacional    | Los cambios en la programación deben respetar los flujos de aprobación establecidos por la institución.                                                         |
| Seguridad      | El acceso a la información se controla mediante autenticación, autorización y gestión de roles.                                                                 |
| Datos          | La información académica y de auditoría debe conservarse conforme a las políticas institucionales de retención documental.                                      |
| Disponibilidad | El sistema debe garantizar disponibilidad para apoyar la operación académica durante los periodos de formación.                                                 |
| Integración    | La comunicación con sistemas externos se realizará mediante mecanismos de integración definidos por la arquitectura del proyecto.                               |

---

# Exclusiones arquitectónicas

Las siguientes decisiones corresponden a la arquitectura del sistema y se documentan en otras secciones del repositorio:

* Arquitectura basada en microservicios.
* Estrategia **Database per Service**.
* Catálogo de eventos de dominio.
* Contratos de APIs.
* Estrategia de auditoría y trazabilidad.
* Patrones de integración entre servicios.

---

# Referencias

* [01-context/overview.md](./overview.md) — Descripción general del proyecto.
* [01-context/glossary.md](./glossary.md) — Definiciones del lenguaje ubicuo.
* [04-requirements/functional.md](../04-requirements/functional.md) — Requerimientos funcionales.
* [04-requirements/non-functional.md](../04-requirements/non-functional.md) — Requerimientos no funcionales.
* [05-architecture/overview.md](../05-architecture/overview.md) — Arquitectura general del sistema.
