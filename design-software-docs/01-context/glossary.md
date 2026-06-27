# Glosario del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

Este glosario define el **lenguaje ubicuo** del proyecto y establece el significado oficial de los términos utilizados en la documentación, el modelo de dominio, los contratos de API, los eventos y las decisiones arquitectónicas. Todos los integrantes del equipo deben utilizar estos conceptos con el mismo significado para garantizar consistencia en el desarrollo del sistema.

---

# Términos del dominio SENA

| Término                   | Definición                                                                                                                                                               | Contexto      |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------- |
| **SENA**                  | Servicio Nacional de Aprendizaje. Entidad pública colombiana encargada de la formación profesional integral mediante programas técnicos, tecnológicos y complementarios. | Institucional |
| **ADSO**                  | Análisis y Desarrollo de Software. Programa de formación del SENA orientado al desarrollo de soluciones de software.                                                     | Institucional |
| **SOFIA Plus**            | Sistema institucional que administra la información académica y administrativa del SENA. Constituye la fuente maestra de información con la que este sistema se integra. | Institucional |
| **Ficha de formación**    | Grupo de aprendices matriculados en un programa de formación durante un periodo determinado. Se asocia con instructores, ambientes, horarios y actividades académicas.   | SENA          |
| **Programa de formación** | Oferta académica oficial del SENA que define competencias, resultados de aprendizaje, duración y perfil de egreso.                                                       | SENA          |
| **Diseño curricular**     | Documento institucional que estructura el programa de formación, sus competencias, RAP y criterios de evaluación.                                                        | SENA          |
| **Competencia**           | Conjunto de conocimientos, habilidades y actitudes que el aprendiz debe desarrollar durante el proceso formativo.                                                        | SENA          |
| **RAP**                   | Resultado de Aprendizaje. Unidad mínima de evaluación asociada a una competencia específica.                                                                             | SENA          |
| **Instructor**            | Profesional responsable de orientar el proceso formativo. Puede impartir formación en varias fichas según su disponibilidad y competencias.                              | SENA          |
| **Aprendiz**              | Persona matriculada en un programa de formación del SENA que participa en el proceso de aprendizaje.                                                                     | SENA          |
| **Centro de formación**   | Sede del SENA donde se desarrollan los programas de formación y se administran los recursos académicos.                                                                  | SENA          |
| **Regional**              | División administrativa del SENA que agrupa uno o varios centros de formación dentro de una zona geográfica.                                                             | SENA          |
| **Jornada**               | Franja de tiempo asignada para el desarrollo de actividades formativas (mañana, tarde o noche).                                                                          | SENA          |
| **Etapa productiva**      | Fase del proceso formativo en la que el aprendiz aplica sus competencias en un entorno laboral real.                                                                     | SENA          |
| **Coordinador académico** | Responsable de supervisar la programación, ejecución y seguimiento de las fichas de formación dentro de un centro.                                                       | SENA          |

---

# Términos del sistema

| Término                         | Definición                                                                                                                                         | Contexto |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| **Horario**                     | Programación de una sesión académica que relaciona una ficha, un instructor, un ambiente y una franja horaria específica.                          | Dominio  |
| **Sesión**                      | Unidad de ejecución de una actividad académica realizada en una fecha y hora determinadas.                                                         | Dominio  |
| **Ambiente de formación**       | Espacio físico destinado al desarrollo de actividades académicas, como aulas, laboratorios o talleres. Posee capacidad, recursos y disponibilidad. | Dominio  |
| **Franja horaria**              | Intervalo de tiempo definido por un día, hora de inicio y hora de finalización sobre el cual se programa una sesión.                               | Dominio  |
| **Conflicto de programación**   | Situación en la que un instructor, ambiente o ficha presenta asignaciones incompatibles dentro de la misma franja horaria.                         | Dominio  |
| **Motor de asignación**         | Componente encargado de generar o validar automáticamente la programación de horarios considerando las restricciones definidas por el negocio.     | Sistema  |
| **Proyecto formativo**          | Conjunto de actividades académicas desarrolladas durante una ficha para alcanzar las competencias definidas en el programa de formación.           | Dominio  |
| **Entregable**                  | Evidencia o producto elaborado por un aprendiz como resultado de una actividad o proyecto formativo.                                               | Dominio  |
| **Validación de restricciones** | Proceso mediante el cual el sistema verifica que una programación cumple todas las reglas de negocio antes de ser registrada.                      | Sistema  |
| **Trazabilidad**                | Capacidad del sistema para registrar y consultar el historial de cambios, programación, ejecución y seguimiento de una actividad académica.        | Sistema  |
| **Ejecución de la sesión**      | Información que refleja lo ocurrido durante una sesión programada, incluyendo asistencia, novedades y evidencias registradas.                      | Dominio  |
| **Novedad**                     | Evento que modifica el desarrollo previsto de una sesión, como cambios de instructor, cancelaciones, reprogramaciones o inasistencias.             | Dominio  |
| **Alerta**                      | Notificación generada automáticamente por el sistema cuando se detecta un conflicto o una condición previamente configurada.                       | Sistema  |
| **Indicador (KPI)**             | Métrica utilizada para evaluar el desempeño del proceso de programación, utilización de recursos o gestión académica.                              | Sistema  |

---

# Términos técnicos del repositorio

| Término                                | Definición                                                                                                                               |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **ADR (Architecture Decision Record)** | Documento que registra una decisión arquitectónica, su contexto, las alternativas evaluadas y sus consecuencias.                         |
| **Bounded Context**                    | Límite dentro del cual un modelo de dominio mantiene un lenguaje ubicuo consistente, según los principios de Domain-Driven Design (DDD). |
| **Database per Service**               | Patrón arquitectónico en el que cada microservicio administra y es propietario de su propia base de datos.                               |
| **Evento de dominio**                  | Suceso relevante del negocio que puede ser publicado para que otros servicios reaccionen de forma desacoplada.                           |
| **Correlation ID**                     | Identificador único que permite rastrear una operación a través de múltiples servicios durante una transacción distribuida.              |
| **Append-only**                        | Estrategia de almacenamiento en la que la información únicamente puede agregarse, preservando el historial de cambios.                   |
| **Dead Letter Queue (DLQ)**            | Cola destinada a almacenar mensajes que no pudieron procesarse correctamente después de agotar los reintentos configurados.              |
| **OpenAPI**                            | Especificación estándar utilizada para documentar contratos de servicios REST y facilitar su interoperabilidad.                          |

---

# Referencias

* [02-domain/entities-and-rules.md](../02-domain/entities-and-rules.md) — Definición de entidades y reglas de negocio.
* [02-domain/domain-map.md](../02-domain/domain-map.md) — Mapa de contextos del dominio.
* [05-architecture/overview.md](../05-architecture/overview.md) — Arquitectura general del sistema.
