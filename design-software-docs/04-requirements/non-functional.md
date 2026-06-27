# Requisitos No Funcionales

> Estado: 🟢 Completo | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Propósito

Este documento define los requisitos de calidad que debe cumplir el Sistema de Gestión de Horarios del SENA.

Los requerimientos no funcionales establecen las características relacionadas con seguridad, rendimiento, disponibilidad, escalabilidad, mantenibilidad y operación de la plataforma, independientemente de las funcionalidades implementadas.

---

# RNF-01 Seguridad

## RNF-01.01 Comunicación segura

Toda comunicación entre clientes, APIs y servicios deberá realizarse mediante HTTPS utilizando TLS 1.3 o superior.

## RNF-01.02 Gestión de contraseñas

Las contraseñas deberán almacenarse utilizando algoritmos de hash seguros (Argon2, bcrypt o equivalente).

## RNF-01.03 Control de acceso

El acceso a los recursos deberá validarse mediante autenticación y autorización basada en roles y permisos.

## RNF-01.04 Gestión de sesiones

Las sesiones deberán utilizar tokens seguros con expiración configurable.

## RNF-01.05 Protección de datos

La información sensible deberá almacenarse utilizando mecanismos de cifrado adecuados.

## RNF-01.06 Auditoría de seguridad

Los eventos relacionados con autenticación, autorización y administración de usuarios deberán registrarse para auditoría.

---

# RNF-02 Disponibilidad

## RNF-02.01 Disponibilidad mínima

La plataforma deberá mantener una disponibilidad anual mínima del **99.5%**.

## RNF-02.02 Recuperación ante fallos

Los servicios críticos deberán contar con mecanismos de recuperación automática.

## RNF-02.03 Respaldo de información

La información deberá respaldarse periódicamente según las políticas institucionales.

## RNF-02.04 Continuidad operativa

La plataforma deberá permitir la restauración de los servicios ante incidentes críticos.

### Métricas

- **RTO:** máximo 4 horas.
- **RPO:** máximo 30 minutos.

---

# RNF-03 Rendimiento

## RNF-03.01 Tiempo de autenticación

El inicio de sesión deberá completarse en menos de **2 segundos**.

## RNF-03.02 Consultas frecuentes

Las consultas de horarios, ambientes e instructores deberán responder en menos de **3 segundos**.

## RNF-03.03 Validación de conflictos

La validación de conflictos de programación deberá responder en menos de **1 segundo**.

## RNF-03.04 Generación de reportes

Los reportes estándar deberán generarse en menos de **10 segundos**.

---

# RNF-04 Escalabilidad

## RNF-04.01 Escalamiento independiente

Cada servicio deberá poder escalar de forma independiente.

## RNF-04.02 Escalabilidad horizontal

Los servicios deberán soportar múltiples instancias.

## RNF-04.03 Crecimiento de usuarios

La solución deberá soportar incrementos progresivos en usuarios concurrentes.

---

# RNF-05 Mantenibilidad

## RNF-05.01 Estándares de desarrollo

El código deberá cumplir los estándares definidos por el proyecto.

## RNF-05.02 Documentación

La documentación funcional, técnica y arquitectónica deberá mantenerse actualizada.

## RNF-05.03 Versionamiento

Las APIs deberán estar versionadas y documentadas.

## RNF-05.04 Pruebas automatizadas

Los componentes deberán contar con pruebas automatizadas.

### Métrica

- Cobertura mínima del **80%**.

---

# RNF-06 Observabilidad

## RNF-06.01 Registro de eventos

Todos los servicios deberán generar registros estructurados.

## RNF-06.02 Monitoreo

La plataforma deberá exponer métricas operativas y de negocio.

## RNF-06.03 Trazabilidad distribuida

Las solicitudes deberán rastrearse mediante **Correlation ID**.

---

# RNF-07 Compatibilidad

## RNF-07.01 Navegadores

La aplicación deberá ser compatible con los navegadores modernos.

## RNF-07.02 Diseño adaptable

La interfaz deberá adaptarse correctamente a escritorio, tablet y dispositivos móviles.

---

# RNF-08 Accesibilidad

## RNF-08.01 Accesibilidad web

La interfaz deberá cumplir las recomendaciones **WCAG 2.1 nivel AA**.

## RNF-08.02 Navegación asistida

La aplicación deberá permitir navegación mediante teclado y tecnologías de asistencia.

---

# RNF-09 Auditoría

## RNF-09.01 Registro de operaciones

Todas las operaciones críticas deberán registrarse.

## RNF-09.02 Conservación de registros

Los registros deberán conservarse conforme a las políticas institucionales.

## RNF-09.03 Integridad de auditoría

Los registros deberán ser inmutables (append-only).

---

# RNF-10 Arquitectura

## RNF-10.01 Independencia de servicios

Cada microservicio deberá desplegarse de forma independiente.

## RNF-10.02 Propiedad de datos

Cada microservicio será propietario exclusivo de su base de datos.

## RNF-10.03 Integración

La comunicación entre servicios deberá realizarse mediante APIs o eventos documentados.

## RNF-10.04 Tolerancia a fallos

La indisponibilidad temporal de un servicio no deberá detener completamente la plataforma.

## RNF-10.05 Consistencia eventual

La sincronización entre servicios deberá realizarse mediante eventos cuando aplique.

---

# Referencias

- [functional.md](./functional.md)
- [../02-domain/domain-map.md](../02-domain/domain-map.md)
- [../05-architecture/overview.md](../05-architecture/overview.md)