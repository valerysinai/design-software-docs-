# Entidades del dominio y reglas operativas

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Arquitectura / Gestión

## Introducción

Este documento describe las entidades principales que conforman el dominio de Horarios SENA, así como las reglas operativas que garantizan la integridad de la información y el correcto funcionamiento de los procesos académicos y administrativos.

Las entidades se encuentran agrupadas según el contexto funcional al que pertenecen dentro de la arquitectura del sistema.

---

## Gestión de Identidad y Acceso

### Usuario

Representa una persona autorizada para interactuar con la plataforma.

**Atributos principales:**

* Identificador único
* Nombre completo
* Correo electrónico
* Estado de la cuenta
* Fecha de último acceso

**Restricciones:**

* El correo electrónico debe ser único.
* Las credenciales deben almacenarse de forma segura mediante mecanismos de cifrado.
* Solo usuarios activos pueden acceder al sistema.

---

### Perfil de Acceso

Define el conjunto de permisos disponibles para un usuario.

**Atributos principales:**

* Nombre del perfil
* Descripción
* Permisos asociados

**Perfiles contemplados:**

* Administrador
* Director
* Coordinador
* Instructor
* Aprendiz

---

### Sesión

Representa una conexión activa dentro de la plataforma.

**Atributos principales:**

* Token de acceso
* Usuario asociado
* Fecha de inicio
* Fecha de expiración
* Dirección IP

**Restricciones:**

* La validez de la sesión está determinada por la configuración de seguridad.
* Una sesión expirada debe invalidarse automáticamente.

---

## Información Institucional

### Centro de Formación

Unidad organizacional donde se desarrollan los procesos formativos.

**Atributos principales:**

* Identificador
* Nombre
* Regional asociada
* Dirección
* Información de contacto

**Restricciones:**

* No pueden existir centros duplicados dentro de una misma regional.

---

### Regional

Agrupa administrativamente varios centros de formación.

**Atributos principales:**

* Identificador
* Nombre
* Ubicación

**Restricciones:**

* El nombre debe ser único dentro de la organización.

---

### Configuración Institucional

Almacena parámetros utilizados por distintos módulos del sistema.

**Atributos principales:**

* Clave
* Valor
* Tipo de dato
* Descripción

**Ejemplos:**

* Máximo de aprendices por ficha
* Horario de inicio de jornada
* Límites de ocupación

---

## Gestión de Ambientes

### Ambiente de Formación

Espacio destinado al desarrollo de actividades académicas.

**Atributos principales:**

* Identificador
* Nombre
* Tipo
* Capacidad
* Centro de formación

**Tipos posibles:**

* Aula
* Laboratorio
* Taller

**Restricciones:**

* La capacidad debe ser mayor a cero.
* El nombre debe ser único dentro del centro.

---

### Disponibilidad de Ambiente

Controla los periodos en los que un ambiente puede utilizarse.

**Atributos principales:**

* Ambiente asociado
* Franja horaria
* Estado de disponibilidad
* Observación

**Restricciones:**

* Las reservas deben respetar los periodos de indisponibilidad registrados.

---

### Recurso de Ambiente

Representa los elementos físicos disponibles dentro de un ambiente.

**Atributos principales:**

* Recurso
* Cantidad
* Estado
* Ambiente asociado

**Ejemplos:**

* Equipos de cómputo
* Proyectores
* Mobiliario
* Herramientas especializadas

---

## Gestión Académica

### Programa de Formación

Agrupa las competencias y resultados de aprendizaje definidos institucionalmente.

**Atributos principales:**

* Código
* Nombre
* Duración
* Competencias asociadas

---

### Competencia

Unidad curricular que integra conocimientos, habilidades y actitudes.

**Atributos principales:**

* Identificador
* Nombre
* Descripción
* Programa asociado

**Restricciones:**

* No puede existir más de una competencia con el mismo nombre dentro del mismo programa.

---

### Resultado de Aprendizaje (RAP)

Elemento específico que define lo que el aprendiz debe demostrar al finalizar una actividad formativa.

**Atributos principales:**

* Identificador
* Nombre
* Competencia asociada
* Criterios de evaluación

---

### Ficha de Formación

Agrupa aprendices, instructores y programación académica dentro de un periodo determinado.

**Atributos principales:**

* Código de ficha
* Programa asociado
* Jornada
* Fecha de inicio
* Coordinador responsable

**Estados posibles:**

* Planeación
* Activa
* Finalizada

**Restricciones:**

* Debe tener aprendices asociados.
* Debe contar con un coordinador responsable.

---

## Gestión de Actores

### Instructor

Persona encargada de orientar el proceso de formación.

**Atributos principales:**

* Identificador
* Nombre
* Especialidades
* Disponibilidad

**Restricciones:**

* Debe poseer al menos una especialidad registrada.
* Solo puede impartir contenidos relacionados con sus competencias.

---

### Aprendiz

Participante inscrito en un programa de formación.

**Atributos principales:**

* Identificador
* Documento
* Nombre
* Estado académico
* Ficha asociada

**Estados posibles:**

* En formación
* Etapa productiva
* Egresado

**Restricciones:**

* Debe pertenecer a una única ficha activa.

---

### Empresa

Entidad vinculada a procesos de etapa productiva o prácticas.

**Atributos principales:**

* Razón social
* NIT
* Sector económico
* Ubicación

**Restricciones:**

* El NIT debe ser único.

---

## Gestión de Horarios

### Horario

Representa la programación académica asignada a una ficha.

**Atributos principales:**

* Identificador
* Ficha
* Instructor
* Ambiente
* Franja horaria
* Sesión asociada

**Estados posibles:**

* Programado
* En ejecución
* Completado
* Cancelado

**Restricciones:**

* Debe cumplir todas las validaciones de disponibilidad y asignación.

---

### Sesión Formativa

Corresponde a la ejecución de una actividad académica programada.

**Atributos principales:**

* Identificador
* Horario asociado
* Ambiente
* Instructor
* RAPs desarrollados

**Restricciones:**

* Debe estar asociada a una programación válida.
* Debe incluir al menos un resultado de aprendizaje.

---

### Conflicto de Programación

Representa una inconsistencia detectada durante la asignación de recursos.

**Atributos principales:**

* Tipo de conflicto
* Elementos involucrados
* Fecha de detección

**Tipos comunes:**

* Doble asignación de instructor
* Doble asignación de ambiente
* Exceso de capacidad

---

## Seguimiento y Monitoreo

### Indicador de Gestión

Métrica utilizada para evaluar el desempeño operativo.

**Ejemplos:**

* Ocupación de ambientes
* Carga horaria de instructores
* Eficiencia de programación

---

### Alerta

Notificación generada cuando un indicador supera los valores esperados.

**Ejemplo:**

* Instructor con sobrecarga horaria.
* Ambiente con ocupación crítica.

---

### Notificación

Comunicación enviada a usuarios del sistema.

**Canales disponibles:**

* Correo electrónico
* Notificaciones internas

---

## Gestión Documental

### Plantilla

Modelo utilizado para generar documentos automáticos.

**Tipos comunes:**

* Reportes
* Certificados
* Actas
* Constancias

---

### Documento

Archivo generado por el sistema a partir de una plantilla.

**Atributos principales:**

* Identificador
* Tipo
* Fecha de generación
* Destinatario

**Restricciones:**

* Toda modificación debe generar una nueva versión.

---

## Auditoría y Trazabilidad

### Registro de Auditoría

Almacena evidencia de las acciones ejecutadas dentro de la plataforma.

**Atributos principales:**

* Fecha y hora
* Usuario responsable
* Operación realizada
* Entidad afectada
* Detalle de cambios

**Restricciones:**

* Los registros son inmutables.
* No pueden ser modificados ni eliminados.
* Deben conservarse según las políticas institucionales de retención.

---

# Reglas operativas del dominio

## RN-01: Exclusividad de asignación

Un instructor no puede estar vinculado a más de una sesión dentro de la misma franja horaria.

Asimismo, un ambiente no puede utilizarse simultáneamente para diferentes actividades académicas.

---

## RN-02: Control de capacidad

La cantidad de aprendices asignados a una sesión debe encontrarse dentro de la capacidad máxima definida para el ambiente.

---

## RN-03: Validación de competencias

Los instructores únicamente pueden ser programados para actividades relacionadas con sus especialidades registradas.

---

## RN-04: Disponibilidad de recursos

Los ambientes solo podrán utilizarse durante periodos en los que se encuentren habilitados y disponibles.

---

## RN-05: Integridad de auditoría

Toda acción relevante ejecutada dentro del sistema debe generar un registro de auditoría permanente.

---

## RN-06: Generación automática de alertas

Los cambios críticos en la programación o el incumplimiento de indicadores deben producir notificaciones automáticas a los responsables correspondientes.

---

## RN-07: Actualización periódica de indicadores

Los indicadores operativos deben recalcularse de forma periódica para mantener información actualizada sobre el estado de la operación.

---

## RN-08: Responsable único por ficha

Cada ficha de formación debe tener un único coordinador responsable durante su ciclo de vida, garantizando la trazabilidad de las decisiones académicas y administrativas.
