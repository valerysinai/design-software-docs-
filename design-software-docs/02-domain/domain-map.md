# Mapa del dominio

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Arquitectura / Gestión

## Visión general de los contextos de negocio

La plataforma **Horarios SENA** está organizada en diferentes contextos de dominio, cada uno responsable de un conjunto específico de procesos y reglas de negocio. Esta división permite mantener una separación clara de responsabilidades y facilita la evolución de la arquitectura basada en microservicios.

---

## Contextos principales

### 1. Gestión de Identidad y Acceso

**Propósito:** Administrar la autenticación de usuarios, el control de acceso y la gestión de permisos dentro de la plataforma.

**Entidades principales:**

* Usuario
* Rol
* Permiso
* Sesión
* Token de acceso

**Términos frecuentes:**

* Inicio de sesión
* Autenticación
* Autorización
* Credenciales
* Permisos

---

### 2. Información Institucional

**Propósito:** Centralizar los datos organizacionales y parámetros compartidos por todos los módulos.

**Entidades principales:**

* Regional
* Centro de Formación
* Ubicación
* Parámetro
* Catálogo

**Términos frecuentes:**

* Regional
* Centro
* Configuración
* Catálogo
* Parámetro

---

### 3. Gestión de Ambientes

**Propósito:** Administrar los espacios físicos destinados al desarrollo de las actividades formativas.

**Entidades principales:**

* Ambiente
* Recurso
* Disponibilidad
* Reserva
* Mantenimiento

**Términos frecuentes:**

* Aula
* Laboratorio
* Taller
* Capacidad
* Disponibilidad

---

### 4. Gestión Académica

**Propósito:** Controlar la estructura curricular y la organización de los procesos formativos.

**Entidades principales:**

* Programa de Formación
* Competencia
* RAP
* Ficha
* Oferta Formativa

**Términos frecuentes:**

* Competencia
* Resultado de aprendizaje
* Programa
* Ficha
* Currículo

---

### 5. Gestión de Actores

**Propósito:** Administrar la información de las personas involucradas en el proceso de formación.

**Entidades principales:**

* Instructor
* Aprendiz
* Empresa
* Etapa Productiva
* Seguimiento

**Términos frecuentes:**

* Instructor
* Aprendiz
* Empresa
* Práctica
* Seguimiento

---

### 6. Gestión de Horarios

**Propósito:** Coordinar la programación académica y validar la disponibilidad de recursos involucrados.

**Entidades principales:**

* Horario
* Sesión
* Franja Horaria
* Asignación
* Conflicto

**Términos frecuentes:**

* Programación
* Agenda
* Disponibilidad
* Asignación
* Conflicto

> Este contexto constituye el núcleo funcional del sistema, ya que articula la información proveniente de los demás dominios.

---

### 7. Seguimiento y Monitoreo

**Propósito:** Supervisar indicadores de gestión, generar alertas y brindar apoyo a la toma de decisiones.

**Entidades principales:**

* Indicador
* Alerta
* Notificación
* Seguimiento
* Plan de Mejoramiento

**Términos frecuentes:**

* KPI
* Métrica
* Alerta
* Desempeño
* Seguimiento

---

### 8. Gestión Documental

**Propósito:** Administrar la creación, almacenamiento y consulta de documentos generados por la plataforma.

**Entidades principales:**

* Documento
* Plantilla
* Versión
* Evidencia

**Términos frecuentes:**

* Reporte
* Acta
* Certificado
* Plantilla
* Archivo

**Naturaleza:** Contexto transversal.

---

### 9. Auditoría y Trazabilidad

**Propósito:** Mantener el historial completo de acciones ejecutadas dentro del sistema.

**Entidades principales:**

* Registro de Auditoría
* Evento
* Historial

**Términos frecuentes:**

* Trazabilidad
* Evidencia
* Registro
* Seguimiento
* Auditoría

**Naturaleza:** Contexto transversal.

---

## Relación entre contextos

```text
┌────────────────────────────────────────────┐
│        GESTIÓN DE HORARIOS (CORE)          │
│  Horarios • Sesiones • Asignaciones        │
└───────────────┬───────────────┬────────────┘
                │               │
                │               │
         Consulta        Utiliza recursos
                │               │
      ┌─────────▼───┐   ┌───────▼────────┐
      │ GESTIÓN     │   │ GESTIÓN DE     │
      │ ACADÉMICA   │   │ AMBIENTES      │
      └──────┬──────┘   └───────┬────────┘
             │                  │
             └──────┬───────────┘
                    │
            ┌───────▼────────┐
            │ GESTIÓN DE     │
            │ ACTORES        │
            └───────┬────────┘
                    │
            ┌───────▼────────┐
            │ INFORMACIÓN    │
            │ INSTITUCIONAL  │
            └───────┬────────┘
                    │
            ┌───────▼────────┐
            │ IDENTIDAD Y    │
            │ ACCESO         │
            └───────┬────────┘
                    │
      ┌─────────────┴─────────────┐
      │ DOCUMENTOS • AUDITORÍA    │
      │      (Transversal)        │
      └─────────────┬─────────────┘
                    │
            ┌───────▼────────┐
            │ MONITOREO Y    │
            │ SEGUIMIENTO    │
            └────────────────┘
```

---

## Principios de interacción

1. Cada contexto mantiene autonomía sobre sus datos y reglas de negocio.
2. La comunicación entre dominios debe realizarse mediante APIs o eventos definidos explícitamente.
3. El contexto de Gestión de Horarios concentra la lógica principal relacionada con la programación académica.
4. Los módulos de Identidad y Acceso proporcionan los mecanismos de autenticación y autorización para toda la plataforma.
5. Auditoría y Gestión Documental funcionan como servicios transversales que apoyan a los demás contextos.
6. El módulo de Monitoreo consume eventos generados por distintos contextos para calcular indicadores y generar alertas operativas.
7. Ningún contexto debe acceder directamente a la base de datos de otro servicio.
8. Toda interacción crítica debe ser trazable mediante mecanismos de auditoría y registro de eventos.

## Consideraciones arquitectónicas

* Patrón aplicado: **Database per Service**.
* Comunicación síncrona mediante APIs REST.
* Comunicación asíncrona mediante eventos de dominio.
* Trazabilidad distribuida mediante identificadores de correlación.
* Separación de responsabilidades basada en principios de Domain-Driven Design (DDD).
