# Eventos del servicio

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Eventos publicados

| Evento | Descripción |
|---------|-------------|
| UserCreated | Se crea un nuevo usuario |
| UserUpdated | Se modifica un usuario |
| UserDisabled | Se desactiva una cuenta |
| LoginSucceeded | Inicio de sesión exitoso |
| LoginFailed | Error de autenticación |

---

## Eventos consumidos

Este servicio consume principalmente solicitudes provenientes del API Gateway para autenticar usuarios y validar permisos.

---

## Servicios consumidores

Los eventos publicados pueden ser utilizados por:

- Audit Service
- Monitoring Service
- Document Service (cuando aplique)

---

## Objetivo

Los eventos permiten mantener desacoplados los procesos de auditoría, monitoreo y notificaciones relacionados con la autenticación y el control de acceso.