# Modelo Conceptual de Datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Objetivo

Este documento describe las principales relaciones entre las entidades del sistema **Gestión de Horarios SENA** desde una perspectiva conceptual.

Su propósito es facilitar la comprensión de la estructura de datos sin depender de un motor de base de datos específico.

---

# Modelo conceptual

```text
Regional
    │
    ▼
Centro de Formación
    │
    ├──────────────┐
    ▼              ▼
Ambiente      Programa de Formación
                   │
                   ▼
             Competencia
                   │
                   ▼
                  RAP
                   │
                   ▼
                 Ficha
            ┌─────┴─────┐
            ▼           ▼
      Instructor   Aprendiz
            │
            ▼
         Horario
            │
            ▼
          Sesión
            │
            ▼
        Documento

Todos los eventos relevantes generan registros en Auditoría.
```

---

# Relaciones principales

| Entidad | Relación | Entidad relacionada |
|----------|----------|---------------------|
| Regional | Contiene | Centro de Formación |
| Centro de Formación | Administra | Ambientes |
| Centro de Formación | Ofrece | Programas de Formación |
| Programa de Formación | Contiene | Competencias |
| Competencia | Incluye | RAP |
| Programa de Formación | Agrupa | Fichas |
| Ficha | Tiene asignados | Aprendices |
| Ficha | Es orientada por | Instructores |
| Horario | Programa | Ficha |
| Horario | Utiliza | Ambiente |
| Horario | Asigna | Instructor |
| Horario | Genera | Sesiones |
| Sesión | Puede generar | Documentos |
| Todos los módulos | Registran | Auditoría |

---

# Principios del modelo

- Las relaciones representan dependencias funcionales y no necesariamente claves foráneas físicas.
- Cada microservicio mantiene la propiedad exclusiva de sus datos.
- Las referencias entre servicios se realizan mediante identificadores (UUID).
- No existen relaciones directas entre bases de datos de diferentes microservicios.
- La sincronización de información se realiza mediante APIs REST y eventos de dominio.

---

# Consideraciones

- Este modelo representa la visión conceptual compartida del sistema.
- Los modelos físicos de cada microservicio se documentan en `09-microservices/services/<servicio>/data-model.md`.
- Las modificaciones al modelo deberán mantenerse alineadas con el dominio y la arquitectura definida para el proyecto.