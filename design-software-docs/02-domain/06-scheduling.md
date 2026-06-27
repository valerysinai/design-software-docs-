# Gestión de Horarios

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio (**Core Domain**)

## Propósito

Administrar la programación académica, asignando instructores, ambientes y franjas horarias a las fichas de formación, garantizando el cumplimiento de las restricciones operativas y académicas.

---

## Horario

Representa la programación académica asignada a una ficha de formación.

### Atributos principales

- Identificador
- Ficha
- Instructor
- Ambiente
- Franja horaria
- Estado

### Estados

- Programado
- En ejecución
- Finalizado
- Cancelado

### Relaciones

- Pertenece a una Ficha de Formación.
- Utiliza un Ambiente.
- Asigna un Instructor.
- Contiene una o varias Sesiones.

### Restricciones

- Debe cumplir todas las validaciones de disponibilidad.
- No puede generar conflictos de programación.

---

## Sesión

Representa la ejecución de una actividad académica programada.

### Atributos principales

- Identificador
- Horario
- Instructor
- Ambiente
- Fecha
- RAP desarrollados

### Relaciones

- Pertenece a un Horario.
- Registra asistencia, novedades y evidencias.

### Restricciones

- Debe estar asociada a un horario válido.
- Debe desarrollar al menos un RAP.

---

## Franja Horaria

Representa un bloque de tiempo utilizado para programar actividades.

### Atributos principales

- Día de la semana
- Hora de inicio
- Hora de finalización

### Restricciones

- La hora de inicio debe ser anterior a la hora de finalización.
- No pueden existir franjas superpuestas para el mismo recurso.

---

## Conflicto de Programación

Representa una inconsistencia detectada durante la asignación de recursos.

### Tipos

- Doble asignación de instructor.
- Doble asignación de ambiente.
- Exceso de capacidad.
- Instructor sin competencia.
- Ambiente no disponible.

### Información registrada

- Tipo
- Fecha
- Recursos involucrados
- Estado

---

## Reglas del contexto

- Un instructor no puede impartir dos sesiones simultáneamente.
- Un ambiente no puede reservarse para dos sesiones en la misma franja.
- La capacidad del ambiente debe ser suficiente para la ficha.
- Toda sesión debe pertenecer a un horario previamente programado.
- Toda modificación del horario debe quedar registrada en auditoría.
- Los conflictos deben detectarse antes de confirmar la programación.