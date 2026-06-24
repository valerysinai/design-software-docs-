# Glosario del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Arquitectura / Gestión

Este glosario establece el lenguaje ubicuo del proyecto. Todos los documentos, contratos de API y eventos de dominio deben usar estos términos con el significado definido aquí.

## Términos del dominio SENA

| Término | Definición | Contexto |
|---------|------------|----------|
| **SENA** | Servicio Nacional de Aprendizaje. Institución pública colombiana que forma trabajadores en programas técnicos y tecnológicos. | Institucional |
| **ADSO** | Análisis y Desarrollo de Sistemas de Información. Programa de formación técnica de ~2 años. | SENA |
| **SOFIA Plus** | Sistema de información institucional del SENA para gestión de la formación. Fuente maestra que este sistema no reemplaza. | Institucional |
| **Ficha de formación** | Agrupación de aprendices que reciben formación en un programa específico durante un periodo. Incluye instructores, ambientes y horarios asignados. | SENA |
| **Instructor** | Formador que imparte competencias. Tiene especialidades, disponibilidad y puede estar asignado a múltiples fichas. | SENA |
| **Aprendiz** | Persona inscrita en un programa de formación SENA. Puede estar en formación complementaria o etapa productiva. | SENA |
| **Programa de formación** | Estructura curricular oficial que define las competencias, RAPs, duración y perfil de egreso. | SENA |
| **Competencia** | Conjunto de conocimientos, habilidades y actitudes que debe dominar el aprendiz. Agrupa múltiples RAPs. | SENA |
| **RAP** | Resultado de Aprendizaje Específico. Unidad mínima de competencia dentro de una competencia. | SENA |
| **Diseño curricular** | Documento oficial que estructura los contenidos, competencias y RAPs de un programa. | SENA |
| **Centro de formación** | Sede física del SENA donde se ofertan programas y se ejecutan fichas. Pertenece a una regional. | SENA |
| **Regional** | División administrativa territorial del SENA. Agrupa varios centros de formación. | SENA |
| **Etapa productiva** | Fase final de formación donde el aprendiz trabaja en una empresa bajo supervisión del SENA. | SENA |
| **Jornada** | Turno de formación: Mañana (6:00–12:00), Tarde (12:00–18:00), Noche (18:00–22:00). | SENA |
| **Coordinador** | Actor institucional responsable de una o más fichas dentro de un centro de formación. | SENA |

## Términos del sistema

| Término | Definición | Contexto |
|---------|------------|----------|
| **Horario** | Asignación específica de instructor, ambiente y ficha en una franja horaria determinada. | Dominio |
| **Sesión** | Instancia de una clase: un instructor imparte a un grupo de aprendices en un ambiente durante un bloque horario. | Dominio |
| **Ambiente** | Espacio físico donde se imparte formación: aula, laboratorio, taller. Tiene capacidad, recursos y disponibilidad. | Dominio |
| **Conflicto** | Solapamiento no permitido: instructor o ambiente asignado a dos fichas simultáneamente en la misma franja. | Dominio |
| **Motor de asignación** | Componente computacional que sugiere horarios automáticamente respetando restricciones de capacidad, disponibilidad y competencias. | Sistema |
| **Franja horaria** | Bloque de tiempo con día de la semana, hora de inicio y hora de fin. Unidad base de la programación. | Dominio |
| **KPI** | Indicador clave de desempeño. Métrica que mide ocupación de ambientes, eficiencia de recursos o carga de instructores. | Dominio |
| **Alerta** | Notificación automática generada cuando un KPI supera un umbral definido. | Dominio |
| **Proyecto formativo** | Conjunto de actividades, entregables, hitos y dependencias que un aprendiz o grupo debe cumplir durante la ficha. | Dominio |
| **Entregable** | Producto concreto que un aprendiz debe entregar en el marco de un proyecto formativo. | Dominio |
| **Validación de restricciones** | Proceso de verificar que una asignación cumple todas las reglas antes de persistirla. | Sistema |
| **Trazabilidad** | Capacidad de seguir el rastro de una sesión, evidencia o decisión desde su origen hasta su estado actual. | Sistema |
| **Ejecución real** | Registro de lo que ocurrió efectivamente en una sesión, en contraste con lo programado. | Dominio |
| **Novedad** | Evento registrado durante una sesión que se aparta del plan: inasistencia, cambio de instructor, incidente. | Dominio |

## Términos técnicos del repositorio

| Término | Definición |
|---------|------------|
| **ADR** | Architecture Decision Record. Documento que registra una decisión arquitectónica, su contexto, alternativas y consecuencias. |
| **Bounded context** | Límite explícito dentro del cual un modelo de dominio aplica con un lenguaje ubicuo coherente. |
| **Database per Service** | Patrón donde cada microservicio posee su propia base de datos, sin compartirla con otros servicios. |
| **Evento de dominio** | Hecho que ocurrió en el negocio y que otros servicios pueden consumir de forma reactiva. |
| **Correlation ID** | Identificador propagado en todas las llamadas de una transacción distribuida para trazabilidad. |
| **Append-only** | Política de base de datos donde solo se permiten inserciones; no se permiten modificaciones ni eliminaciones. |
| **Dead Letter Queue (DLQ)** | Cola donde van los mensajes/eventos que no pudieron procesarse tras los reintentos configurados. |
| **OpenAPI** | Especificación estándar para describir contratos de APIs REST. |

## Referencias

- [02-domain/entities-and-rules.md](../02-domain/entities-and-rules.md) — Entidades y reglas de negocio detalladas
- [02-domain/domain-map.md](../02-domain/domain-map.md) — Mapa de contextos acotados