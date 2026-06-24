# ADR-003: Autenticación mediante JWT

**Estado:** APPROVED
**Fecha:** 2026-06-24
**Autores:** Por definir
**Equipos involucrados:** Arquitectura, Seguridad

---

## Contexto

Los microservicios requieren un mecanismo de autenticación distribuido que permita validar usuarios sin mantener sesiones compartidas.

La solución debe soportar escalabilidad horizontal y bajo acoplamiento.

## Decisión

Se decide utilizar JWT (JSON Web Token) como mecanismo principal de autenticación.

La gestión de identidad se realizará mediante OAuth2/OpenID Connect.

Los tokens serán emitidos por IAM Service y validados por API Gateway y los servicios consumidores.

## Consecuencias

### Positivas

* Arquitectura stateless.
* Escalabilidad horizontal.
* Menor dependencia entre servicios.

### Negativas / Trade-offs

* Complejidad en la revocación de tokens.
* Gestión adicional de expiraciones y renovación.

### Riesgos

* Uso indebido de tokens comprometidos.
* Configuraciones incorrectas de expiración.

## Alternativas consideradas

| Alternativa          | Por qué se descartó               |
| -------------------- | --------------------------------- |
| Sesiones en servidor | Limita la escalabilidad           |
| Autenticación básica | No cumple requisitos de seguridad |

## Referencias

* ../../cross-cutting.md
* ../../../04-requirements/non-functional.md
