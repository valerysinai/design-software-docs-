# Eventos del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

## Propósito

Este documento describe los principales **eventos de dominio** generados por el Sistema de Gestión de Horarios del SENA.

Los eventos representan hechos relevantes que ya ocurrieron dentro del negocio y permiten la comunicación entre los distintos contextos del dominio sin acoplamiento directo.

---

# Convenciones

Todos los eventos publicados por el sistema deben cumplir las siguientes características:

| Característica | Descripción       |
| -------------- | ----------------- |
| Tipo           | Evento de dominio |
| Identificador  | UUID              |
| Fecha          | Timestamp UTC     |
| Correlation ID | Obligatorio       |
| Versionado     | Permitido         |
| Estado         | Inmutable         |

---

# Catálogo de eventos

## Gestión de Identidad y Acceso

### UsuarioRegistrado

**Descripción**

Se publica cuando un nuevo usuario es creado dentro de la plataforma.

**Contexto publicador**

* Gestión de Identidad y Acceso

**Contextos consumidores**

* Auditoría
* Seguimiento y Monitoreo

**Información principal**

* Id del usuario
* Correo electrónico
* Rol asignado
* Fecha de creación

---

### UsuarioDesactivado

**Descripción**

Se publica cuando un usuario es deshabilitado.

**Consumidores**

* Auditoría
* Gestión de Horarios
* Seguimiento y Monitoreo

**Información principal**

* Usuario
* Motivo
* Fecha

---

### UsuarioAutenticado

**Descripción**

Se genera después de una autenticación exitosa.

**Consumidores**

* Auditoría
* Seguimiento y Monitoreo

**Información principal**

* Usuario
* Dirección IP
* Fecha
* Correlation ID

---

# Información Institucional

### ConfiguracionActualizada

**Descripción**

Se publica cuando cambia un parámetro institucional.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Parámetro
* Valor anterior
* Nuevo valor

---

# Gestión Académica

### FichaCreada

**Descripción**

Se genera al registrar una nueva ficha de formación.

**Consumidores**

* Gestión de Horarios
* Auditoría
* Gestión Documental

**Información principal**

* Código
* Programa
* Centro
* Jornada
* Coordinador

---

### FichaActualizada

**Descripción**

Se publica cuando una ficha modifica su información.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Id de ficha
* Cambios realizados

---

### FichaFinalizada

**Descripción**

Se genera cuando una ficha termina su ciclo de formación.

**Consumidores**

* Gestión Documental
* Seguimiento y Monitoreo
* Auditoría

**Información principal**

* Ficha
* Fecha de finalización

---

### AprendizAsignado

**Descripción**

Se genera cuando un aprendiz es vinculado a una ficha.

**Consumidores**

* Auditoría
* Gestión de Horarios

**Información principal**

* Aprendiz
* Ficha

---

# Gestión de Actores

### InstructorRegistrado

**Descripción**

Se genera al registrar un instructor.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Instructor
* Especialidades
* Centro

---

### InstructorActualizado

**Descripción**

Se publica cuando cambia la disponibilidad o información del instructor.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Instructor
* Datos modificados

---

# Gestión de Ambientes

### AmbienteRegistrado

**Descripción**

Se genera al crear un nuevo ambiente.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Ambiente
* Tipo
* Capacidad

---

### AmbienteBloqueado

**Descripción**

Indica que un ambiente queda temporalmente fuera de servicio.

**Consumidores**

* Gestión de Horarios
* Auditoría

**Información principal**

* Ambiente
* Motivo
* Periodo

---

### AmbienteLiberado

**Descripción**

Indica que un ambiente vuelve a estar disponible.

**Consumidores**

* Gestión de Horarios

**Información principal**

* Ambiente
* Fecha

---

# Gestión de Horarios

### HorarioProgramado

**Descripción**

Se genera cuando una programación ha sido validada correctamente.

**Consumidores**

* Auditoría
* Gestión Documental
* Seguimiento y Monitoreo

**Información principal**

* Horario
* Instructor
* Ambiente
* Ficha
* Franja horaria

---

### ConflictoDetectado

**Descripción**

Se publica cuando el sistema identifica una inconsistencia durante la programación.

**Consumidores**

* Auditoría
* Seguimiento y Monitoreo

**Información principal**

* Tipo
* Recursos involucrados
* Descripción

---

### HorarioCancelado

**Descripción**

Se genera cuando una programación es anulada.

**Consumidores**

* Auditoría
* Gestión Documental

**Información principal**

* Horario
* Motivo

---

### SesionFinalizada

**Descripción**

Confirma la finalización de una sesión académica.

**Consumidores**

* Seguimiento y Monitoreo
* Gestión Documental
* Auditoría

**Información principal**

* Sesión
* Horario
* Asistencia registrada

---

### AsignacionAutomaticaProcesada

**Descripción**

Resultado de la ejecución del motor automático de asignación.

**Consumidores**

* Seguimiento y Monitoreo
* Auditoría

**Información principal**

* Horarios generados
* Restricciones evaluadas
* Conflictos encontrados

---

# Seguimiento y Monitoreo

### IndicadoresActualizados

**Descripción**

Se publica cuando los indicadores operativos son recalculados.

**Consumidores**

* Auditoría

**Información principal**

* Fecha
* Indicadores calculados

---

### AlertaGenerada

**Descripción**

Se genera cuando un indicador supera un umbral establecido.

**Consumidores**

* Auditoría
* Notificaciones

**Información principal**

* Tipo
* Prioridad
* Valor registrado

---

### NotificacionEnviada

**Descripción**

Confirma el envío de una notificación.

**Consumidores**

* Auditoría

**Información principal**

* Destinatario
* Canal
* Fecha

---

# Gestión Documental

### DocumentoGenerado

**Descripción**

Se genera cuando el sistema crea un documento automáticamente.

**Consumidores**

* Auditoría

**Información principal**

* Documento
* Plantilla
* Destinatario

---

### DocumentoConsultado

**Descripción**

Se publica cuando un documento es visualizado o descargado.

**Consumidores**

* Auditoría

**Información principal**

* Documento
* Usuario
* Fecha

---

# Auditoría

### OperacionAuditada

**Descripción**

Representa el registro permanente de una operación realizada en cualquier contexto.

**Consumidores**

* Servicio de Auditoría

**Información principal**

* Usuario
* Operación
* Entidad
* Fecha
* Correlation ID

---

# Principios

* Los eventos representan hechos que ya ocurrieron.
* Los eventos son inmutables.
* Cada evento tiene un único contexto publicador.
* Un mismo evento puede ser consumido por varios contextos.
* Los consumidores nunca modifican el evento recibido.
* Todos los eventos relevantes deben quedar registrados en Auditoría.

---

# Flujos representativos

## Creación de una ficha

```text
Gestión Académica
        │
        ▼
   FichaCreada
        │
        ├── Gestión de Horarios
        ├── Auditoría
        └── Gestión Documental
```

---

## Programación de horarios

```text
Gestión de Horarios
        │
        ▼
 HorarioProgramado
        │
        ├── Auditoría
        ├── Gestión Documental
        └── Seguimiento y Monitoreo
```

Si ocurre un conflicto:

```text
Gestión de Horarios
        │
        ▼
 ConflictoDetectado
        │
        ├── Auditoría
        └── Seguimiento y Monitoreo
```

---

## Finalización de una sesión

```text
Gestión de Horarios
        │
        ▼
 SesionFinalizada
        │
        ├── Seguimiento y Monitoreo
        ├── Gestión Documental
        └── Auditoría
```
