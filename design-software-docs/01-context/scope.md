# Alcance del proyecto

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Arquitectura / Gestión

## En alcance

1. Controlar horarios programados y ejecución real por ficha, instructor y ambiente.
2. Registrar trazabilidad precisa de sesiones de formación (asistencia, novedades, incidencias).
3. Gestionar avance de fichas y aprendices en tiempo real.
4. Relacionar proyectos formativos con programas, diseño curricular, competencias, RAPs, evidencias y entregables.
5. Identificar dependencias entre proyectos formativos.
6. Detectar y registrar conflictos de asignación (solapamiento de instructor o ambiente).
7. Proveer motor de asignación automática basado en restricciones.
8. Generar reportes, actas y documentos PDF mediante worker asincrónico.
9. Enviar notificaciones y alertas a instructores, coordinadores y directivos.
10. Exponer eventos de dominio y contratos por microservicio.
11. Proveer tablero runtime de avance y desviaciones (KPIs).
12. Auditoría append-only completa de todas las operaciones con retención mínima de 7 años.
13. Gestionar datos de referencia: centros, regiones, parámetros, catálogos.
14. Sincronización con fuentes maestras externas sin reemplazarlas.

## Fuera de alcance

1. **No reemplazar SOFIA Plus** ni crear fuente maestra institucional sin autorización explícita.
2. Gestión de nóminas o contratos de instructores.
3. Evaluación y calificaciones de aprendices (sistema de notas).
4. Plataforma de aprendizaje virtual (LMS).
5. Registro y control de asistencia biométrica.
6. Integración con sistemas financieros o presupuestales.
7. Gestión de eventos externos (seminarios, conferencias fuera del plan de formación).
8. Exportación a formatos propietarios de terceros (SAP, Oracle, etc.).
9. Mezcla de horarios, evidencias, proyectos, aprendices y diseño curricular en un solo servicio.
10. Uso de prompts como mecanismo principal de seguridad.
11. Acciones destructivas sin políticas y aprobación explícita.

## Supuestos

- Existen instructores y ambientes registrados previamente en el sistema.
- Las fichas de formación siguen un calendario académico definido por el SENA.
- Los usuarios tienen acceso a navegadores web modernos con conectividad estable.
- Los datos de entrada (competencias, RAPs, disponibilidades) son validados antes del ingreso.
- La capacidad computacional disponible es suficiente para cálculos de asignación en tiempo real.

## Restricciones

| Tipo | Restricción |
|------|-------------|
| Regulatoria | Cumplimiento con normativas internas del SENA sobre gobernanza de datos y Ley 1581 de 2012 |
| Técnica | Tiempo de respuesta del motor de asignación < 5 segundos para fichas típicas |
| Operacional | Las asignaciones no pueden cambiar sin autorización explícita del director de centro |
| Seguridad | Auditoría append-only: no se puede modificar un registro una vez creado |
| Datos | Retención mínima de 7 años para registros de auditoría |
| Acceso | Control de acceso basado en roles: DIRECTOR, COORDINADOR, INSTRUCTOR, APRENDIZ, ADMIN |
| Arquitectura | Cada microservicio tiene su propia base de datos (Database per Service Pattern) |
| Integración | Acceso entre microservicios solo vía API, evento o contrato explícito; no joins cross-BD |

## Referencias

- [01-context/overview.md](./overview.md) — Contexto general y objetivos
- [04-requirements/functional.md](../04-requirements/functional.md) — Requerimientos funcionales
- [04-requirements/non-functional.md](../04-requirements/non-functional.md) — Requerimientos no funcionales
- [05-architecture/decisions/records/ADR-001-no-sofia-plus-replacement.md](../05-architecture/decisions/records/ADR-001-no-sofia-plus-replacement.md)