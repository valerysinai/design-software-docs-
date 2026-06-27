# Matriz de Trazabilidad

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Establecer la relación entre los requisitos funcionales, las historias de usuario y los principales componentes del sistema para garantizar la cobertura funcional, facilitar el seguimiento del desarrollo y apoyar las actividades de validación y pruebas.

---

# Matriz de trazabilidad

| Módulo | Requisito Funcional | Historia de Usuario | Microservicio / Componente |
|---------|---------------------|---------------------|----------------------------|
| Gestión de Identidad y Acceso | RF-01.01 | HU-001 | auth-service |
| Gestión de Identidad y Acceso | RF-01.02 | HU-002 | auth-service |
| Gestión de Identidad y Acceso | RF-01.03 | HU-002 | auth-service |
| Información Institucional | RF-02.01 | HU-005 | reference-service |
| Información Institucional | RF-02.02 | HU-005 | reference-service |
| Gestión de Ambientes | RF-03.01 | HU-006 | environment-service |
| Gestión de Ambientes | RF-03.03 | HU-006 | environment-service |
| Parametrización | RF-04.01 | HU-002 | reference-service |
| Parametrización | RF-04.02 | HU-002 | reference-service |
| Gestión Académica | RF-05.01 | HU-003 | academic-service |
| Gestión Académica | RF-05.04 | HU-004 | academic-service |
| Gestión Académica | RF-05.05 | HU-004 | academic-service |
| Gestión de Fichas y Proyectos | RF-06.01 | HU-014 | project-service |
| Gestión de Fichas y Proyectos | RF-06.02 | HU-005 | academic-service |
| Gestión de Fichas y Proyectos | RF-06.03 | HU-005 | academic-service |
| Gestión de Actores | RF-07.01 | HU-007 | actor-service |
| Gestión de Actores | RF-07.02 | HU-008 | actor-service |
| Gestión de Horarios | RF-08.01 | HU-009 | scheduling-service |
| Gestión de Horarios | RF-08.02 | HU-007 | scheduling-service |
| Gestión de Horarios | RF-08.03 | HU-009 | scheduling-service |
| Gestión de Horarios | RF-08.05 | HU-011 | scheduling-service |
| Gestión de Horarios | RF-08.06 | HU-009 | scheduling-service |
| Seguimiento y Monitoreo | RF-09.01 | HU-012 | monitoring-service |
| Seguimiento y Monitoreo | RF-09.02 | HU-017 | notification-service |

---

# Cobertura funcional

| Módulo | Cobertura |
|---------|-----------|
| Gestión de Identidad y Acceso | ✔ |
| Información Institucional | ✔ |
| Gestión de Ambientes | ✔ |
| Parametrización | ✔ |
| Gestión Académica | ✔ |
| Gestión de Fichas y Proyectos | ✔ |
| Gestión de Actores | ✔ |
| Gestión de Horarios | ✔ |
| Seguimiento y Monitoreo | ✔ |

---

# Beneficios

- Verificar que cada requisito funcional tenga al menos una historia de usuario asociada.
- Facilitar el análisis de impacto cuando se modifique un requisito.
- Servir como base para la construcción de casos de prueba.
- Mantener la alineación entre análisis, desarrollo, pruebas y arquitectura.
- Identificar rápidamente el microservicio responsable de cada funcionalidad.

---

# Referencias

- [functional.md](./functional.md)
- [non-functional.md](./non-functional.md)
- [user-stories.md](./user-stories.md)
- [../02-domain/domain-map.md](../02-domain/domain-map.md)
- [../05-architecture/service-catalog.md](../05-architecture/service-catalog.md)