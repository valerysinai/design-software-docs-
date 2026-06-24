# Eventos del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Arquitectura / Gestión

## Catálogo de eventos del sistema

Los eventos de dominio representan hechos relevantes ocurridos dentro de la plataforma. Estos eventos permiten la comunicación entre contextos de negocio y facilitan la trazabilidad, auditoría y automatización de procesos.

---

## Contexto de Identidad y Acceso

### RegistroUsuario

**Descripción:** Se genera cuando un nuevo usuario es incorporado al sistema.

**Servicios interesados:**

* Auditoría
* Notificaciones

**Información transmitida:**

* Identificador del usuario
* Correo electrónico
* Perfil asignado
* Fecha de creación

### DesactivacionUsuario

**Descripción:** Ocurre cuando un administrador inhabilita una cuenta.

**Servicios interesados:**

* Gestión de Horarios
* Auditoría
* Notificaciones

**Información transmitida:**

* Usuario afectado
* Motivo de desactivación
* Fecha del cambio

### AccesoAutorizado

**Descripción:** Se registra después de una autenticación exitosa.

**Servicios interesados:**

* Auditoría
* Monitoreo

**Información transmitida:**

* Usuario autenticado
* Dirección IP
* Fecha y hora de acceso

---

## Contexto de Configuración y Parámetros

### ConfiguracionActualizada

**Descripción:** Indica la modificación de un parámetro utilizado por el sistema.

**Servicios interesados:**

* Auditoría
* Gestión de Horarios

**Información transmitida:**

* Identificador del parámetro
* Valor anterior
* Nuevo valor

---

## Contexto Académico

### CreacionFichaFormacion

**Descripción:** Se produce al registrar una nueva ficha de formación.

**Servicios interesados:**

* Gestión de Horarios
* Auditoría
* Notificaciones

**Información transmitida:**

* Código de ficha
* Programa asociado
* Centro de formación
* Jornada
* Coordinador responsable

### ActualizacionFichaFormacion

**Descripción:** Notifica cambios realizados sobre una ficha existente.

**Servicios interesados:**

* Auditoría
* Gestión de Horarios
* Notificaciones

**Información transmitida:**

* Identificador de ficha
* Detalle de modificaciones realizadas

### CierreFichaFormacion

**Descripción:** Se genera cuando una ficha culmina su ciclo formativo.

**Servicios interesados:**

* Documentación
* Monitoreo
* Auditoría

**Información transmitida:**

* Ficha finalizada
* Fecha de cierre

### VinculacionAprendiz

**Descripción:** Registro de un aprendiz asociado a una ficha.

**Servicios interesados:**

* Auditoría
* Notificaciones

**Información transmitida:**

* Aprendiz
* Ficha asignada

---

## Contexto de Actores

### AltaInstructor

**Descripción:** Registro de un nuevo instructor dentro de la plataforma.

**Servicios interesados:**

* Auditoría
* Gestión de Horarios

**Información transmitida:**

* Instructor
* Especialidades
* Centro de formación

### ModificacionInstructor

**Descripción:** Cambios relacionados con disponibilidad o perfil del instructor.

**Servicios interesados:**

* Gestión de Horarios
* Auditoría
* Notificaciones

**Información transmitida:**

* Instructor afectado
* Datos modificados

---

## Contexto de Infraestructura

### RegistroAmbiente

**Descripción:** Creación de un nuevo ambiente de formación.

**Servicios interesados:**

* Gestión de Horarios
* Auditoría

**Información transmitida:**

* Ambiente
* Capacidad
* Ubicación

### BloqueoAmbiente

**Descripción:** Indica que un ambiente deja de estar disponible temporalmente.

**Servicios interesados:**

* Gestión de Horarios
* Auditoría

**Información transmitida:**

* Ambiente afectado
* Periodo de indisponibilidad
* Motivo

### LiberacionAmbiente

**Descripción:** Restablece la disponibilidad de un ambiente previamente bloqueado.

**Servicios interesados:**

* Notificaciones
* Auditoría

**Información transmitida:**

* Ambiente habilitado

---

## Contexto de Gestión de Horarios

### ProgramacionConfirmada

**Descripción:** Se genera cuando una asignación cumple todas las validaciones establecidas.

**Servicios interesados:**

* Auditoría
* Notificaciones
* Gestión documental

**Información transmitida:**

* Horario
* Instructor
* Ambiente
* Ficha
* Franja horaria

### InconsistenciaDetectada

**Descripción:** Identificación de conflictos durante la programación.

**Servicios interesados:**

* Auditoría
* Notificaciones

**Información transmitida:**

* Tipo de conflicto
* Elementos involucrados
* Descripción

### ProgramacionAnulada

**Descripción:** Cancelación de una asignación previamente creada.

**Servicios interesados:**

* Auditoría
* Notificaciones
* Gestión documental

**Información transmitida:**

* Horario afectado
* Motivo de cancelación

### FinalizacionSesion

**Descripción:** Confirmación de que una sesión académica fue completada.

**Servicios interesados:**

* Monitoreo
* Auditoría
* Gestión documental

**Información transmitida:**

* Sesión
* Horario asociado
* Número de asistentes

### AsignacionAutomaticaProcesada

**Descripción:** Resultado de la ejecución del motor de programación automática.

**Servicios interesados:**

* Auditoría
* Monitoreo
* Notificaciones

**Información transmitida:**

* Horarios sugeridos
* Restricciones evaluadas
* Conflictos encontrados

---

## Contexto de Monitoreo

### IndicadoresActualizados

**Descripción:** Actualización periódica de métricas operativas.

**Servicios interesados:**

* Auditoría
* Notificaciones

**Información transmitida:**

* Fecha de cálculo
* Indicadores obtenidos

### AlertaOperativaGenerada

**Descripción:** Generación automática de alertas derivadas de métricas fuera de rango.

**Servicios interesados:**

* Monitoreo
* Auditoría
* Notificaciones

**Información transmitida:**

* Tipo de alerta
* Valor registrado
* Umbral definido

### MensajeNotificado

**Descripción:** Registro del envío de una notificación a un usuario.

**Servicios interesados:**

* Auditoría

**Información transmitida:**

* Destinatario
* Canal utilizado
* Contenido enviado

---

## Contexto Documental

### ArchivoGenerado

**Descripción:** Creación de documentos oficiales o reportes.

**Servicios interesados:**

* Auditoría
* Gestión documental

**Información transmitida:**

* Documento generado
* Plantilla utilizada
* Destinatario

### ArchivoConsultado

**Descripción:** Descarga o visualización de un documento almacenado.

**Servicios interesados:**

* Auditoría

**Información transmitida:**

* Documento
* Usuario
* Fecha de acceso

---

## Contexto de Auditoría

### AccionAuditada

**Descripción:** Registro permanente de operaciones ejecutadas dentro de la plataforma.

**Servicios interesados:**

* Servicio de Auditoría

**Información transmitida:**

* Fecha y hora
* Usuario responsable
* Acción realizada
* Entidad afectada
* Estado anterior y posterior

---

## Flujos representativos de eventos

### Flujo de creación de ficha

```text
Usuario
   │
   ▼
CreacionFichaFormacion
   ├── Auditoría
   ├── Gestión de Horarios
   └── Notificaciones
```

### Flujo de programación automática

```text
Motor de Asignación
   │
   ▼
AsignacionAutomaticaProcesada
   ├── Auditoría
   ├── Monitoreo
   └── Notificaciones

Si existen inconsistencias:

AsignacionAutomaticaProcesada
          │
          ▼
InconsistenciaDetectada
          │
          └── Alerta a coordinadores
```

### Flujo de cierre de ficha

```text
Sistema
   │
   ▼
CierreFichaFormacion
   ├── Gestión Documental
   ├── Monitoreo
   ├── Auditoría
   └── Notificaciones
```
