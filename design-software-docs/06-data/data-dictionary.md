# Diccionario de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Objetivo

Este documento describe las principales entidades de datos utilizadas por la plataforma **Gestión de Horarios SENA**, sus atributos más relevantes y las convenciones generales para la persistencia de la información.

---

# Entidades principales

## Ficha

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| programaId | Programa de formación asociado. |
| centroId | Centro de formación responsable. |
| jornada | Jornada académica. |
| periodo | Periodo de formación vigente. |
| estado | Planeación, Activa o Finalizada. |
| fechaCreacion | Fecha de creación del registro. |

---

## Ambiente

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| centroId | Centro donde se encuentra ubicado. |
| nombre | Nombre del ambiente. |
| tipo | Aula, Laboratorio o Taller. |
| capacidad | Número máximo de aprendices. |
| estado | Disponible, Mantenimiento o Inhabilitado. |
| recursos | Recursos disponibles en el ambiente. |

---

## Instructor

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| nombre | Nombre completo. |
| documento | Documento de identificación. |
| especialidad | Área de formación principal. |
| estado | Activo o Inactivo. |

---

## Aprendiz

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| nombre | Nombre completo. |
| documento | Documento de identidad. |
| fichaId | Ficha de formación asignada. |
| estado | En formación, Etapa productiva o Egresado. |

---

## Horario

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| fichaId | Ficha programada. |
| ambienteId | Ambiente asignado. |
| instructorId | Instructor responsable. |
| fechaInicio | Fecha y hora de inicio. |
| fechaFin | Fecha y hora de finalización. |
| estado | Programado, En ejecución, Finalizado o Cancelado. |

---

## Documento

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| tipo | Acta, Reporte, Certificado o Notificación. |
| propietarioId | Usuario o entidad relacionada. |
| estado | Generado, Enviado o Archivado. |
| url | Ubicación del archivo generado. |

---

## Registro de Auditoría

| Campo | Descripción |
|--------|-------------|
| id | Identificador único (UUID). |
| usuarioId | Usuario que ejecutó la acción. |
| operacion | Acción realizada. |
| servicio | Microservicio que originó el evento. |
| fecha | Fecha y hora del registro. |

---

# Convenciones generales

- Todos los identificadores utilizarán el tipo **UUID**.
- Las fechas se almacenarán utilizando el estándar **ISO 8601 (UTC)**.
- Los estados deberán utilizar valores controlados mediante **ENUM**.
- Cada microservicio será propietario de sus propios datos (**Database per Service**).
- No se permiten relaciones directas entre bases de datos de diferentes microservicios.
- La integración de información entre servicios se realizará mediante **APIs REST** o **eventos de dominio**.

---

# Observaciones

- Este diccionario representa el modelo de datos compartido del sistema.
- Los detalles específicos de cada microservicio deberán documentarse en `09-microservices/services/<servicio>/data-model.md`.
- Cualquier modificación en los atributos deberá mantenerse sincronizada con las APIs y las migraciones de base de datos.