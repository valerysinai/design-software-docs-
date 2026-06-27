# Calidad

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir | Equipo: Por definir

## Contenido

Documenta las prácticas de aseguramiento de la calidad del software, incluyendo la estrategia de pruebas, los criterios para la revisión de código y las buenas prácticas que garantizan la estabilidad, mantenibilidad y confiabilidad de la plataforma.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [testing-strategy.md](./testing-strategy.md) | Estrategia de pruebas funcionales, técnicas y de integración | 🟡 |
| [code-review.md](./code-review.md) | Criterios y proceso para la revisión de código | 🟡 |

---

## Objetivos

La documentación de calidad busca:

- Garantizar la calidad del software durante todo el ciclo de desarrollo.
- Detectar errores de forma temprana.
- Mantener un código limpio y mantenible.
- Asegurar el cumplimiento de los requisitos funcionales y no funcionales.
- Promover buenas prácticas de desarrollo colaborativo.

---

## Alcance

Esta carpeta documenta:

- Estrategia de pruebas.
- Tipos de pruebas.
- Cobertura mínima esperada.
- Criterios de aceptación.
- Flujo de revisión de código.
- Estándares de calidad antes de integrar cambios.

---

## Relación con otras carpetas

| Carpeta | Relación |
|---------|----------|
| `04-requirements` | Los requisitos son validados mediante pruebas. |
| `07-api` | Las APIs son verificadas durante las pruebas de integración. |
| `09-microservices` | Cada servicio debe implementar sus pruebas correspondientes. |
| `10-devops` | El pipeline CI/CD ejecuta automáticamente las pruebas y validaciones de calidad. |