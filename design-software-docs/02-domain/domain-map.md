# Mapa del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-24
> Autor: Por definir | Equipo: Por definir

## Visión general de los contextos de negocio

El **Sistema de Gestión de Horarios del SENA** está organizado en diferentes **contextos acotados (Bounded Contexts)**, cada uno responsable de un conjunto específico de procesos, reglas de negocio y entidades del dominio. Esta separación permite mantener un lenguaje ubicuo consistente, reducir el acoplamiento entre componentes y facilitar la evolución de la arquitectura basada en microservicios.

Cada contexto posee autonomía sobre sus datos y lógica de negocio, interactuando con los demás únicamente mediante contratos bien definidos, APIs o eventos de dominio.

---

# Contextos principales

## 1. Gestión de Identidad y Acceso

**Propósito:** Administrar la autenticación, autorización y gestión de identidades de los usuarios que interactúan con la plataforma.

**Entidades principales:**

* Usuario
* Rol
* Permiso
* Sesión
* Token de acceso

**Lenguaje ubicuo:**

* Inicio de sesión
* Autenticación
* Autorización
* Credenciales
* Permisos

---

## 2. Información Institucional

**Propósito:** Administrar la información institucional compartida utilizada por los diferentes módulos del sistema.

**Entidades principales:**

* Regional
* Centro de Formación
* Ubicación
* Parámetro
* Catálogo

**Lenguaje ubicuo:**

* Regional
* Centro
* Configuración
* Catálogo
* Parámetro

---

## 3. Gestión de Ambientes

**Propósito:** Gestionar los ambientes de formación y los recursos físicos requeridos para el desarrollo de las actividades académicas.

**Entidades principales:**

* Ambiente
* Recurso
* Disponibilidad
* Reserva
* Mantenimiento

**Lenguaje ubicuo:**

* Aula
* Laboratorio
* Taller
* Capacidad
* Disponibilidad

---

## 4. Gestión Académica

**Propósito:** Administrar la estructura académica que soporta el proceso formativo, incluyendo programas, fichas de formación, competencias y resultados de aprendizaje.

**Entidades principales:**

* Programa de Formación
* Competencia
* RAP
* Ficha
* Oferta Formativa

**Lenguaje ubicuo:**

* Competencia
* Resultado de aprendizaje
* Programa
* Ficha
* Diseño curricular

---

## 5. Gestión de Actores

**Propósito:** Administrar la información de las personas y organizaciones que participan en el proceso de formación.

**Entidades principales:**

* Instructor
* Aprendiz
* Empresa
* Etapa Productiva

**Lenguaje ubicuo:**

* Instructor
* Aprendiz
* Empresa
* Práctica
* Formación

---

## 6. Gestión de Horarios (**Core Domain**)

**Propósito:** Coordinar la programación académica, validar restricciones y gestionar la asignación de recursos necesarios para cada sesión de formación.

**Entidades principales:**

* Horario
* Sesión
* Franja Horaria
* Asignación
* Conflicto

**Lenguaje ubicuo:**

* Programación
* Agenda
* Disponibilidad
* Asignación
* Conflicto

> Este contexto constituye el **núcleo funcional (Core Domain)** del sistema, ya que concentra la lógica principal relacionada con la programación académica y coordina la interacción con los demás contextos.

---

## 7. Seguimiento y Monitoreo

**Propósito:** Supervisar la operación del sistema mediante indicadores, alertas y mecanismos de seguimiento que apoyen la toma de decisiones.

**Entidades principales:**

* Indicador
* KPI
* Dashboard
* Alerta
* Notificación

**Lenguaje ubicuo:**

* KPI
* Métrica
* Alerta
* Desempeño
* Seguimiento

---

## 8. Gestión Documental

**Propósito:** Administrar la creación, generación, almacenamiento y consulta de documentos asociados al proceso formativo.

**Entidades principales:**

* Documento
* Plantilla
* Versión
* Evidencia

**Lenguaje ubicuo:**

* Reporte
* Acta
* Certificado
* Plantilla
* Archivo

**Naturaleza:** Contexto transversal.

---

## 9. Auditoría y Trazabilidad

**Propósito:** Registrar de forma inmutable las operaciones realizadas dentro de la plataforma para garantizar trazabilidad y cumplimiento.

**Entidades principales:**

* Registro de Auditoría
* Evento
* Historial

**Lenguaje ubicuo:**

* Trazabilidad
* Evidencia
* Registro
* Auditoría
* Historial

**Naturaleza:** Contexto transversal.

---

# Relación entre contextos

```text
                    ┌───────────────────────────────┐
                    │   GESTIÓN DE HORARIOS         │
                    │        (CORE DOMAIN)          │
                    └──────────────┬────────────────┘
                                   │
                 Consume información del dominio
                                   │
        ┌──────────────┬───────────┼──────────────┐
        │              │           │              │
        ▼              ▼           ▼              ▼
 GESTIÓN         GESTIÓN      GESTIÓN      INFORMACIÓN
 ACADÉMICA      ACTORES      AMBIENTES    INSTITUCIONAL

                                   │
                                   ▼
                     IDENTIDAD Y ACCESO (IAM)
                     Autenticación y autorización

          DOCUMENTAL ─────────────── AUDITORÍA
                  │                       │
                  └──────────┬────────────┘
                             ▼
                  SEGUIMIENTO Y MONITOREO
                  Consume eventos del dominio
```

---

# Principios de interacción

1. Cada contexto mantiene la propiedad exclusiva de sus datos y reglas de negocio.
2. La comunicación entre contextos se realiza mediante contratos API o eventos de dominio claramente definidos.
3. El contexto **Gestión de Horarios** constituye el **Core Domain** y coordina el proceso de programación académica.
4. El contexto **Gestión de Identidad y Acceso** proporciona los mecanismos de autenticación y autorización utilizados por toda la plataforma.
5. **Gestión Documental** y **Auditoría** son contextos transversales que prestan servicios al resto del sistema.
6. **Seguimiento y Monitoreo** consume eventos publicados por otros contextos para generar indicadores y alertas.
7. Ningún contexto accede directamente a la base de datos de otro contexto.
8. Toda interacción relevante debe ser trazable mediante auditoría y mecanismos de correlación de eventos.

---

# Consideraciones arquitectónicas

* Se aplica el patrón **Database per Service**, garantizando la autonomía de los datos de cada contexto.
* La comunicación síncrona entre contextos se realiza mediante contratos API claramente definidos.
* La integración asíncrona utiliza eventos de dominio para minimizar el acoplamiento entre servicios.
* La trazabilidad distribuida se implementa mediante identificadores de correlación (**Correlation ID**).
* La separación de responsabilidades sigue los principios de **Domain-Driven Design (DDD)**.

---

# Referencias

* [entities-and-rules.md](./entities-and-rules.md) — Entidades, agregados y reglas de negocio.
* [domain-events.md](./domain-events.md) — Eventos del dominio e interacciones entre contextos.
* [../05-architecture/overview.md](../05-architecture/overview.md) — Arquitectura general del sistema.
