# Catálogo de Servicios

> Estado: 🟢 Completo | Última actualización: 2026-06-23
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura y Desarrollo

## Objetivo

Registro centralizado de los microservicios que conforman la plataforma Gestión de Horarios SENA.

Cada servicio representa un dominio de negocio independiente y es responsable de su lógica, persistencia e integración.

---

# Servicios de Dominio

| Servicio                     | Base de Datos | Dominio                          | Estado |
| ---------------------------- | ------------- | -------------------------------- | ------ |
| iam-service                  | iam_db        | Gestión de identidad y acceso    | 🟡     |
| reference-data-service       | ref_db        | Datos maestros y parametrización | 🟡     |
| academic-management-service  | academic_db   | Gestión académica                | 🟡     |
| training-environment-service | env_db        | Ambientes y recursos             | 🟡     |
| scheduling-service           | scheduling_db | Programación académica           | 🟡     |
| actors-service               | actors_db     | Gestión de actores               | 🟡     |
| document-service             | document_db   | Gestión documental               | 🟡     |
| monitoring-service           | monitoring_db | Indicadores y monitoreo          | 🟡     |
| audit-service                | audit_db      | Auditoría y trazabilidad         | 🟡     |

---

# Catálogo de Entidades por Servicio

## iam-service

**Base de datos:** `iam_db`

Entidades:

* usuario
* rol
* permiso
* sesion
* token

Responsabilidades:

* Autenticación.
* Autorización.
* Gestión de roles.
* Gestión de permisos.
* Administración de sesiones.

---

## reference-data-service

**Base de datos:** `ref_db`

Entidades:

* macroregion
* centro_formacion
* catalogo
* estado
* parametro

Responsabilidades:

* Parametrización institucional.
* Catálogos maestros.
* Configuración del sistema.

---

## academic-management-service

**Base de datos:** `academic_db`

Entidades:

* programa
* competencia
* RAP
* ficha
* oferta

Responsabilidades:

* Programas de formación.
* Competencias.
* Resultados de aprendizaje.
* Fichas.
* Oferta académica.

---

## training-environment-service

**Base de datos:** `env_db`

Entidades:

* ambiente
* inventario
* mantenimiento
* reserva
* disponibilidad

Responsabilidades:

* Gestión de ambientes.
* Disponibilidad.
* Inventario.
* Mantenimiento.

---

## scheduling-service

**Base de datos:** `scheduling_db`

Entidades:

* horario
* sesion_clase
* franja
* asignacion
* conflicto

Responsabilidades:

* Programación académica.
* Asignación de recursos.
* Detección de conflictos.
* Gestión de sesiones.

---

## actors-service

**Base de datos:** `actors_db`

Entidades:

* instructor
* aprendiz
* empresa
* etapa_productiva
* bitacora

Responsabilidades:

* Gestión de instructores.
* Gestión de aprendices.
* Empresas.
* Seguimiento de etapa productiva.

---

## document-service

**Base de datos:** `document_db`

Entidades:

* documento
* version
* plantilla

Responsabilidades:

* Gestión documental.
* Versionamiento.
* Plantillas institucionales.

---

## monitoring-service

**Base de datos:** `monitoring_db`

Entidades:

* seguimiento_kpi
* alerta
* notificacion
* sesion_seguimiento
* plan_mejoramiento

Responsabilidades:

* KPIs.
* Dashboards.
* Alertas.
* Seguimiento institucional.

---

## audit-service

**Base de datos:** `audit_db`

Entidades:

* auditoria

Responsabilidades:

* Registro histórico.
* Trazabilidad.
* Evidencia de operaciones.
* Cumplimiento normativo.

Modelo:

```text
Append Only
```

No se permiten actualizaciones ni eliminaciones.

---

# Componentes Desplegables

## iam-service

* iam-api

---

## reference-data-service

* reference-data-api

---

## academic-management-service

* academic-management-api

---

## training-environment-service

* training-environment-api

---

## scheduling-service

* schedules-api
* scheduling-engine-worker
* conflict-validator-worker

---

## actors-service

* actors-api

---

## document-service

* document-api
* template-api
* pdf-renderer-worker
* document-lifecycle-worker

---

## monitoring-service

* monitoring-api
* alert-worker

---

## audit-service

* audit-worker

---

# Resumen de Arquitectura

| Métrica                  | Valor                |
| ------------------------ | -------------------- |
| Microservicios           | 9                    |
| Bases de datos           | 9                    |
| Componentes desplegables | 16                   |
| Patrón de persistencia   | Database per Service |
| Integración síncrona     | REST                 |
| Integración asíncrona    | Eventos              |
| Autenticación            | JWT + OAuth2         |
| Auditoría                | Append Only          |

---

# Dependencias Principales

```text
Scheduling Service
    ├── Academic Management Service
    ├── Actors Service
    └── Training Environment Service

Monitoring Service
    └── Consume eventos de todos los dominios

Audit Service
    └── Consume eventos de todos los dominios
```

---

# Referencias

* communication-patterns.md
* event-catalog.md
* ../05-architecture/overview.md
* ../05-architecture/decisions/records/ADR-001-arquitectura-microservicios.md
* ../05-architecture/decisions/records/ADR-004-base-datos-por-servicio.md
