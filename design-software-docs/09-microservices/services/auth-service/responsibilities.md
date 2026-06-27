# Responsabilidades del IAM Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El IAM Service administra la identidad de los usuarios y controla el acceso a los recursos del sistema.

---

## Responsabilidades

- Registrar usuarios.
- Actualizar información de usuarios.
- Gestionar roles y permisos.
- Autenticar usuarios.
- Administrar sesiones.
- Emitir y validar tokens JWT.
- Registrar eventos de autenticación.

---

## Límites del servicio

Este servicio **no administra**:

- Horarios.
- Ambientes.
- Programas de formación.
- Documentos.
- Auditoría.

Estas funciones pertenecen a otros microservicios.

---

## Servicios relacionados

| Servicio | Relación |
|----------|----------|
| API Gateway | Valida el acceso a las APIs |
| Audit Service | Registra eventos de seguridad |
| Monitoring Service | Monitorea accesos y autenticaciones |