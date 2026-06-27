# API

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Contenido

Esta sección define los lineamientos para el diseño, implementación y consumo de las APIs del sistema **Gestión de Horarios SENA**.

Incluye las convenciones de diseño, el mecanismo de autenticación y la ubicación de los contratos OpenAPI publicados para los consumidores internos y externos.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [guidelines.md](./guidelines.md) | Convenciones y buenas prácticas para el diseño de APIs REST | 🟡 |
| [authentication.md](./authentication.md) | Estrategia de autenticación, autorización y seguridad | 🟡 |
| [contracts/openapi/](./contracts/openapi/) | Contratos OpenAPI oficiales publicados | 🟡 |

---

## Organización de contratos

| Tipo de contrato | Ubicación | Propósito |
|-----------------|-----------|-----------|
| Contrato del servicio (en desarrollo) | `09-microservices/services/<servicio>/api-contract.md` | Documentación utilizada durante el desarrollo del microservicio |
| Contrato OpenAPI oficial | `07-api/contracts/openapi/<servicio>.yaml` | Versión aprobada y publicada para consumidores |

---

## Principios

- Todas las APIs siguen el estilo **REST**.
- Los contratos se documentan mediante **OpenAPI 3.x**.
- La autenticación se realiza mediante **JWT** validado por el API Gateway.
- Las respuestas utilizan formatos consistentes para datos y errores.
- Las APIs deben mantener compatibilidad entre versiones para evitar afectar a los consumidores.

---

## Relación con otras carpetas

- **02-domain:** define las entidades y reglas del negocio.
- **04-requirements:** especifica los requisitos que implementan las APIs.
- **05-architecture:** describe la arquitectura que soporta la comunicación entre servicios.
- **09-microservices:** contiene los contratos de trabajo de cada microservicio durante el desarrollo.
