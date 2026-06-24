# Vista General de Arquitectura

> Estado: 🟢 Completo | Última actualización: 2026-06-22
> Autor: Por definir

## Arquitectura General

El sistema Gestión de Horarios SENA adopta una arquitectura basada en microservicios orientada a dominios de negocio (Domain-Oriented Architecture).

Cada dominio funcional es implementado como un servicio independiente responsable de su lógica de negocio, persistencia y contratos de integración.

## Objetivos Arquitectónicos

* Separación de responsabilidades.
* Escalabilidad independiente.
* Alta mantenibilidad.
* Despliegue autónomo por servicio.
* Trazabilidad de operaciones.
* Integración desacoplada.

## Microservicios

### IAM Service

Responsable de:

* Autenticación
* Autorización
* Usuarios
* Roles
* Permisos
* Gestión de sesiones

Base de datos propia.

---

### Academic Management Service

Responsable de:

* Programas de formación
* Competencias
* Resultados de aprendizaje (RAP)
* Diseños curriculares
* Fichas
* Oferta académica

Base de datos propia.

---

### Actors Service

Responsable de:

* Instructores
* Aprendices
* Empresas
* Coordinadores
* Directivos

Base de datos propia.

---

### Training Environment Service

Responsable de:

* Ambientes
* Inventario
* Recursos físicos
* Disponibilidad

Base de datos propia.

---

### Scheduling Service

Responsable de:

* Programación académica
* Horarios
* Sesiones
* Asignaciones
* Validación de conflictos
* Incidencias

Base de datos propia.

---

### Reference Data Service

Responsable de:

* Catálogos
* Parametrización
* Configuración institucional

Base de datos propia.

---

### Document Service

Responsable de:

* Gestión documental
* Plantillas
* Versionamiento

Base de datos propia.

---

### Monitoring Service

Responsable de:

* KPIs
* Métricas
* Reportes
* Dashboards

Base de datos propia.

---

### Audit Service

Responsable de:

* Registro de eventos
* Trazabilidad
* Auditoría inmutable

Base de datos propia.

## Flujo General

Frontend → API Gateway → Microservicios → Bases de Datos

## Principios Arquitectónicos

* Database per Service.
* API First.
* Stateless Services.
* Domain-Driven Design.
* Event-Driven Integration.
* Observabilidad desde el diseño.
* Seguridad por defecto.

## Dependencias

Scheduling Service consume información de:

* Academic Management Service
* Actors Service
* Training Environment Service

Monitoring Service consume eventos provenientes de todos los servicios.

Audit Service registra eventos generados por todos los servicios.
