# Vista General de Arquitectura

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Arquitectura general

La plataforma **Gestión de Horarios SENA** implementa una arquitectura basada en **microservicios** y principios de **Domain-Driven Design (DDD)**.

Cada microservicio es responsable de un dominio específico del negocio, posee su propia base de datos y se comunica con los demás mediante APIs REST y eventos de dominio, garantizando bajo acoplamiento y alta cohesión.

La arquitectura busca facilitar la escalabilidad, el mantenimiento, la evolución independiente de cada servicio y la trazabilidad completa de las operaciones.

---

# Objetivos arquitectónicos

- Separar responsabilidades por dominio de negocio.
- Permitir el despliegue independiente de cada servicio.
- Facilitar el mantenimiento y evolución del sistema.
- Garantizar la trazabilidad de todas las operaciones.
- Reducir el acoplamiento entre componentes.
- Facilitar la integración con sistemas externos.

---

# Microservicios del sistema

## IAM Service

Responsable de:

- Autenticación
- Autorización
- Usuarios
- Roles
- Permisos
- Gestión de sesiones

**Base de datos:** Propia.

---

## Academic Management Service

Responsable de:

- Programas de formación
- Competencias
- Resultados de aprendizaje (RAP)
- Diseño curricular
- Fichas de formación

**Base de datos:** Propia.

---

## Actors Service

Responsable de:

- Aprendices
- Instructores
- Coordinadores
- Directivos
- Empresas (etapa productiva)

**Base de datos:** Propia.

---

## Training Environment Service

Responsable de:

- Ambientes
- Recursos
- Inventario
- Disponibilidad
- Reservas

**Base de datos:** Propia.

---

## Scheduling Service

Servicio central del sistema.

Responsable de:

- Programación de horarios
- Asignación de instructores
- Asignación de ambientes
- Validación de restricciones
- Gestión de sesiones
- Detección de conflictos

**Base de datos:** Propia.

---

## Reference Data Service

Responsable de:

- Regionales
- Centros de formación
- Catálogos
- Parámetros institucionales
- Configuración general

**Base de datos:** Propia.

---

## Monitoring Service

Responsable de:

- KPIs
- Indicadores
- Alertas
- Notificaciones
- Dashboard operativo

**Base de datos:** Propia.

---

## Document Service

Responsable de:

- Generación de documentos
- Plantillas
- Versiones
- Reportes
- Actas

**Base de datos:** Propia.

---

## Audit Service

Responsable de:

- Auditoría
- Registro de eventos
- Historial de operaciones
- Trazabilidad

**Base de datos:** Propia.

---

# Flujo general de la arquitectura

```text
                 Frontend Web
                       │
                       ▼
                 API Gateway
                       │
 ┌─────────────────────┼──────────────────────┐
 │                     │                      │
 ▼                     ▼                      ▼
IAM Service     Scheduling Service    Academic Service
 │                     │                      │
 ▼                     ▼                      ▼
Actors Service  Environment Service  Reference Data
 │                     │                      │
 └──────────────┬──────┴──────────────┘
                ▼
        Monitoring Service
                │
        ┌───────┴────────┐
        ▼                ▼
 Document Service   Audit Service
```

---

# Principios arquitectónicos

- Arquitectura basada en microservicios.
- Domain-Driven Design (DDD).
- Database per Service.
- API First.
- Integración mediante eventos de dominio.
- Servicios sin estado (Stateless).
- Observabilidad desde el diseño.
- Seguridad por defecto.
- Escalabilidad independiente por servicio.

---

# Relaciones entre servicios

El **Scheduling Service** consume información proveniente de:

- Academic Management Service
- Actors Service
- Training Environment Service
- Reference Data Service

El **Monitoring Service** recibe eventos emitidos por todos los microservicios para generar indicadores y alertas.

El **Audit Service** registra todas las operaciones críticas ejecutadas dentro de la plataforma.

El **Document Service** genera documentos y reportes a partir de la información suministrada por los demás servicios.

---

# Referencias

- [02-domain/domain-map.md](../02-domain/domain-map.md) — Contextos de dominio.
- [03-product/modules.md](../03-product/modules.md) — Módulos funcionales.
- [04-requirements/functional.md](../04-requirements/functional.md) — Requisitos funcionales.
- [05-architecture/cross-cutting.md](./cross-cutting.md) — Componentes transversales.
- [05-architecture/deployment.md](./deployment.md) — Vista de despliegue.