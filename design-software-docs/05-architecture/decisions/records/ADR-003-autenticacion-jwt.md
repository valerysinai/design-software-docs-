# ADR-003: Autenticación mediante JWT

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir
> Equipo: Arquitectura de Software

---

## Contexto

La plataforma **Gestión de Horarios SENA** está compuesta por múltiples microservicios que requieren un mecanismo de autenticación distribuido, seguro y escalable.

La solución debe evitar el uso de sesiones compartidas entre servicios, facilitar el despliegue independiente y permitir que cada solicitud pueda validarse sin depender del estado del servidor.

---

## Decisión

Se adopta **JWT (JSON Web Token)** como mecanismo principal de autenticación para la plataforma.

La gestión de identidad será centralizada mediante el **IAM Service**, utilizando los estándares **OAuth2** y **OpenID Connect**.

Los tokens serán:

- Emitidos por el IAM Service.
- Validados por el API Gateway.
- Verificados por los microservicios cuando sea necesario.
- Configurados con tiempos de expiración y mecanismos de renovación mediante Refresh Tokens.

Esta estrategia permite mantener una arquitectura **Stateless**, adecuada para una solución basada en microservicios.

---

## Consecuencias

### Positivas

- Arquitectura sin estado (Stateless).
- Escalabilidad horizontal.
- Bajo acoplamiento entre servicios.
- Validación distribuida de identidad.
- Integración sencilla con APIs y aplicaciones web.

### Negativas / Trade-offs

- Mayor complejidad para revocar tokens antes de su expiración.
- Necesidad de administrar tiempos de expiración y renovación.
- Requiere proteger adecuadamente las claves de firma.

### Riesgos

- Uso indebido de tokens comprometidos.
- Configuración incorrecta del tiempo de expiración.
- Exposición de credenciales por malas prácticas del cliente.

---

## Alternativas consideradas

| Alternativa | Motivo del descarte |
|-------------|---------------------|
| Sesiones almacenadas en servidor | Limitan la escalabilidad horizontal y generan dependencia del estado del servidor. |
| Autenticación básica (Basic Auth) | No proporciona un nivel de seguridad adecuado para la plataforma. |
| API Keys | No permiten gestionar usuarios, roles y permisos de forma eficiente. |

---

## Impacto arquitectónico

### Componentes afectados

- API Gateway
- IAM Service
- Frontend Web

### Servicios afectados

- IAM Service
- Todos los microservicios consumidores de APIs

### Datos afectados

- Usuarios
- Roles
- Permisos
- Tokens de acceso
- Sesiones

---

## Estado de implementación

| Actividad | Estado |
|-----------|--------|
| Diseño | ☑ |
| Desarrollo | ☐ |
| Pruebas | ☐ |
| Producción | ☐ |

---

## Referencias

- [../cross-cutting.md](../cross-cutting.md) — Aspectos transversales.
- [../overview.md](../overview.md) — Vista general de arquitectura.
- [../../04-requirements/non-functional.md](../../04-requirements/non-functional.md) — Requisitos no funcionales.
- [../../02-domain/entities-and-rules/README.md](../../02-domain/entities-and-rules/README.md) — Entidades y reglas del dominio.