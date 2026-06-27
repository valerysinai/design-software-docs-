# DevOps

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir | Equipo: Por definir

## Contenido

Documenta la preparación del entorno de desarrollo, la estrategia de integración y despliegue continuo (CI/CD), y los diferentes ambientes utilizados durante el ciclo de vida del proyecto.

Esta documentación garantiza que todos los integrantes del equipo puedan configurar el proyecto, ejecutar los servicios localmente y desplegar nuevas versiones de forma estandarizada.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [local-setup.md](./local-setup.md) | Configuración del entorno local de desarrollo | 🟡 |
| [ci-cd.md](./ci-cd.md) | Estrategia de integración y despliegue continuo | 🟡 |
| [environments.md](./environments.md) | Ambientes del proyecto y reglas de uso | 🟡 |

---

## Alcance

La documentación de esta carpeta cubre:

- Configuración del entorno local.
- Requisitos de software para el desarrollo.
- Ejecución de microservicios.
- Gestión de variables de entorno.
- Estrategia de CI/CD.
- Despliegue mediante contenedores.
- Ambientes de Desarrollo, Integración, Calidad y Producción.

---

## Relación con otras carpetas

| Carpeta | Relación |
|---------|----------|
| `05-architecture` | Define la arquitectura que será desplegada. |
| `07-api` | Las APIs son validadas durante el pipeline CI/CD. |
| `09-microservices` | Los servicios documentados aquí son desplegados mediante la estrategia DevOps. |