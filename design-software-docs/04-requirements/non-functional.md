# Requisitos No Funcionales

> Estado: 🟢 Completo | Última actualización: 2026-06-22
> Autor: Por definir
> Equipo: Arquitectura de Software

---

# RNF-01 Seguridad

## RNF-01.01 Comunicación segura

Toda comunicación entre clientes, APIs y servicios deberá realizarse mediante HTTPS utilizando TLS 1.3 o superior.

## RNF-01.02 Gestión de contraseñas

Las contraseñas deberán almacenarse utilizando algoritmos de hash seguros como Argon2, bcrypt o equivalente.

## RNF-01.03 Control de acceso

El acceso a recursos protegidos deberá validarse mediante mecanismos de autenticación y autorización basados en roles y permisos.

## RNF-01.04 Gestión de sesiones

Las sesiones deberán utilizar tokens seguros con expiración configurable.

## RNF-01.05 Protección de datos

La información sensible deberá almacenarse utilizando mecanismos de cifrado adecuados.

## RNF-01.06 Auditoría de seguridad

Todos los eventos relacionados con autenticación, autorización y administración de usuarios deberán registrarse para auditoría.

---

# RNF-02 Disponibilidad

## RNF-02.01 Disponibilidad mínima

La plataforma deberá mantener una disponibilidad anual mínima del 99.5%.

## RNF-02.02 Recuperación ante fallos

Los servicios críticos deberán contar con mecanismos de recuperación automática ante fallos.

## RNF-02.03 Respaldo de información

La información deberá respaldarse periódicamente mediante políticas definidas por la institución.

## RNF-02.04 Continuidad operativa

La plataforma deberá permitir la restauración de los servicios ante incidentes críticos.

### Métricas

* RTO (Recovery Time Objective): máximo 4 horas.
* RPO (Recovery Point Objective): máximo 30 minutos.

---

# RNF-03 Rendimiento

## RNF-03.01 Tiempo de autenticación

Las operaciones de inicio de sesión deberán completarse en menos de 2 segundos bajo condiciones normales.

## RNF-03.02 Consultas frecuentes

Las consultas de horarios, ambientes e instructores deberán responder en menos de 3 segundos.

## RNF-03.03 Validación de conflictos

La detección de conflictos de programación deberá realizarse en tiempo real y responder en menos de 1 segundo.

## RNF-03.04 Generación de reportes

Los reportes estándar deberán generarse en menos de 10 segundos.

---

# RNF-04 Escalabilidad

## RNF-04.01 Escalamiento independiente

La arquitectura deberá permitir el crecimiento independiente de cada servicio o módulo.

## RNF-04.02 Escalabilidad horizontal

Los servicios deberán soportar escalamiento horizontal sin afectar la operación de otros componentes.

## RNF-04.03 Crecimiento de usuarios

La solución deberá soportar incrementos progresivos en usuarios concurrentes y volumen de operaciones.

---

# RNF-05 Mantenibilidad

## RNF-05.01 Estándares de desarrollo

El código fuente deberá cumplir los estándares de calidad definidos por el proyecto.

## RNF-05.02 Documentación

La documentación funcional, técnica y arquitectónica deberá mantenerse actualizada.

## RNF-05.03 Versionamiento

Las APIs deberán encontrarse versionadas y documentadas.

## RNF-05.04 Pruebas automatizadas

Los componentes deberán contar con pruebas automatizadas que garanticen la estabilidad de la solución.

### Métrica

* Cobertura mínima de pruebas: 80%.

---

# RNF-06 Observabilidad

## RNF-06.01 Registro de eventos

Todos los servicios deberán generar registros estructurados de eventos y errores.

## RNF-06.02 Monitoreo

La plataforma deberá permitir monitorear métricas operativas y de negocio.

## RNF-06.03 Trazabilidad

Las solicitudes deberán poder rastrearse entre los diferentes servicios mediante identificadores de correlación.

---

# RNF-07 Compatibilidad

## RNF-07.01 Navegadores

La aplicación deberá ser compatible con las versiones vigentes de los navegadores modernos.

## RNF-07.02 Dispositivos

La interfaz deberá adaptarse correctamente a dispositivos de escritorio, tabletas y móviles.

---

# RNF-08 Accesibilidad

## RNF-08.01 Accesibilidad web

La interfaz deberá cumplir las recomendaciones WCAG 2.1 nivel AA.

## RNF-08.02 Navegación asistida

La aplicación deberá ser utilizable mediante teclado y tecnologías de asistencia.

---

# RNF-09 Auditoría

## RNF-09.01 Registro de operaciones

Todas las operaciones críticas deberán generar registros auditables.

## RNF-09.02 Conservación de registros

Los registros históricos deberán conservarse según las políticas institucionales definidas por el SENA.

## RNF-09.03 Integridad de auditoría

Los registros de auditoría no deberán poder ser modificados por usuarios finales.

---

# RNF-10 Cumplimiento Arquitectónico

## RNF-10.01 Independencia de servicios

Cada servicio deberá ser desplegable de forma independiente.

## RNF-10.02 Propiedad de datos

Cada servicio será responsable de su propia base de datos y modelo de persistencia.

## RNF-10.03 Contratos de integración

La comunicación entre servicios deberá realizarse mediante APIs definidas y documentadas.

## RNF-10.04 Tolerancia a fallos

La indisponibilidad temporal de un servicio no deberá comprometer completamente la operación de la plataforma.
