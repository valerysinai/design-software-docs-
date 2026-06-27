# Estrategia de Migración de Esquemas

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Objetivo

Definir la estrategia para administrar la evolución de los esquemas de base de datos del sistema **Gestión de Horarios SENA**, garantizando consistencia, trazabilidad y compatibilidad entre versiones de los diferentes microservicios.

---

# Principios

- Cada microservicio administra de forma independiente las migraciones de su propia base de datos.
- Las modificaciones de esquema deben estar versionadas y ser reproducibles.
- Ninguna migración podrá modificar directamente la base de datos de otro servicio.
- Las migraciones deberán ejecutarse automáticamente durante el proceso de despliegue.

---

# Flujo de migración

```text
Cambio en el modelo de datos
            │
            ▼
Creación de migración versionada
            │
            ▼
Validación en ambiente de desarrollo
            │
            ▼
Pruebas de integración
            │
            ▼
Despliegue en ambiente de calidad
            │
            ▼
Despliegue en producción
```

---

# Versionado

Cada migración deberá contar con:

- Identificador único.
- Fecha de creación.
- Descripción del cambio.
- Autor responsable.
- Script de aplicación.
- Script de reversión cuando sea posible.

Ejemplo:

| Versión | Descripción |
|----------|-------------|
| V1.0.0 | Creación del esquema inicial |
| V1.1.0 | Incorporación de la entidad Horario |
| V1.2.0 | Inclusión de índices para optimización |

---

# Buenas prácticas

- Mantener compatibilidad con versiones anteriores cuando sea posible.
- Evitar cambios destructivos en ambientes productivos.
- Probar todas las migraciones antes de su liberación.
- Documentar cualquier cambio que afecte APIs o eventos de dominio.

---

# Relación con la arquitectura

La estrategia de migración sigue los principios definidos en la arquitectura del proyecto:

- **Database per Service**.
- Independencia de despliegue de cada microservicio.
- Integración mediante APIs REST y eventos de dominio.
- Trazabilidad de todos los cambios realizados sobre la estructura de datos.

---

# Consideraciones

- Cada servicio es responsable de la evolución de su propio esquema.
- Las migraciones deben mantenerse sincronizadas con la documentación de `09-microservices`.
- Todo cambio estructural deberá reflejarse en el diccionario de datos y en el modelo conceptual cuando corresponda.