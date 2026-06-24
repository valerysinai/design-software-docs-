# Requisitos No Funcionales

> Estado: 🟡 En progreso | Última actualización: 2026-06-22
> Autor: Por definir | Equipo: Por definir

## Seguridad

* Toda comunicación deberá realizarse mediante HTTPS.
* Las contraseñas deberán almacenarse cifradas.
* Los permisos deberán validarse en cada solicitud protegida.
* Los accesos deberán registrarse para auditoría.

## Disponibilidad

* La plataforma deberá mantener una disponibilidad mínima del 99%.
* Los servicios críticos deberán contar con mecanismos de recuperación ante fallos.

## Rendimiento

* Las consultas frecuentes deberán responder en menos de 3 segundos.
* La validación de conflictos de horarios deberá realizarse en tiempo real.

## Escalabilidad

* La arquitectura deberá permitir el crecimiento independiente de cada módulo.
* Los servicios deberán soportar incrementos progresivos de usuarios y operaciones.

## Mantenibilidad

* El código deberá seguir estándares definidos por el proyecto.
* La documentación deberá mantenerse actualizada.
* Las APIs deberán encontrarse versionadas.

## Auditoría

* Todas las operaciones críticas deberán generar registros auditables.
* Los registros históricos deberán conservarse según las políticas institucionales.

## Compatibilidad

* La plataforma deberá funcionar en navegadores modernos.
* La interfaz deberá ser compatible con dispositivos de escritorio y móviles.
