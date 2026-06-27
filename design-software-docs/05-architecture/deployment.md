# Arquitectura de Despliegue

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

## Objetivo

Describir la distribución lógica de los componentes de la plataforma y los ambientes donde será desplegada la solución basada en microservicios.

---

# Ambientes de despliegue

## Desarrollo (Development)

Ambiente utilizado por los desarrolladores para implementar nuevas funcionalidades y realizar pruebas locales.

## Integración (Integration)

Ambiente destinado a validar la comunicación entre microservicios y verificar los contratos de integración.

## Calidad (QA)

Ambiente utilizado para ejecutar pruebas funcionales, de aceptación y validaciones antes de producción.

## Producción (Production)

Ambiente disponible para los usuarios finales, con alta disponibilidad, monitoreo y políticas de seguridad.

---

# Componentes de la arquitectura

## Frontend

Aplicación web responsable de la interacción con los usuarios del sistema.

Funciones principales:

- Inicio de sesión.
- Gestión de horarios.
- Administración académica.
- Consultas y reportes.

---

## API Gateway

Punto único de entrada hacia los microservicios.

Responsabilidades:

- Enrutamiento de solicitudes.
- Validación de autenticación (JWT).
- Rate Limiting.
- Balanceo de carga.
- Registro de solicitudes.

---

## Microservicios

La plataforma está compuesta por los siguientes servicios:

- IAM Service
- Academic Management Service
- Actors Service
- Training Environment Service
- Scheduling Service
- Reference Data Service
- Monitoring Service
- Document Service
- Audit Service

Cada servicio es independiente y administra su propia lógica de negocio.

---

## Bases de datos

Cada microservicio posee una base de datos independiente siguiendo el patrón **Database per Service**, evitando dependencias directas entre dominios.

---

## Message Broker

Componente encargado de la comunicación asíncrona entre los servicios mediante eventos de dominio.

Permite:

- Publicación de eventos.
- Consumo de eventos.
- Desacoplamiento entre servicios.
- Procesamiento asíncrono.

---

## Sistema de monitoreo

Responsable de centralizar:

- Logs.
- Métricas.
- Alertas.
- Trazabilidad distribuida.
- Estado de los servicios.

---

# Diagrama lógico

```text
                 Usuario
                    │
                    ▼
              Frontend Web
                    │
                    ▼
              API Gateway
                    │
     ┌──────────────┼──────────────┐
     ▼              ▼              ▼
 IAM Service   Scheduling    Academic Service
                   │
      ┌────────────┼─────────────┐
      ▼            ▼             ▼
 Actors      Environment    Reference Data
      │            │             │
      └────────────┼─────────────┘
                   ▼
            Message Broker
                   │
        ┌──────────┴──────────┐
        ▼                     ▼
 Monitoring Service     Audit Service
                   │
                   ▼
          Document Service
```

---

# Contenerización

Todos los microservicios deberán desplegarse mediante contenedores Docker, garantizando portabilidad y consistencia entre ambientes.

---

# Orquestación

Para ambientes de integración y producción se recomienda utilizar Kubernetes, permitiendo:

- Escalamiento automático.
- Alta disponibilidad.
- Balanceo de carga.
- Recuperación automática ante fallos.

---

# Escalabilidad

La arquitectura permite el escalamiento horizontal independiente de cada microservicio según la demanda del negocio.

---

# Principios de despliegue

- Despliegue independiente por servicio.
- Infraestructura desacoplada.
- Configuración mediante variables de entorno.
- Comunicación mediante APIs y eventos.
- Observabilidad desde el despliegue.
- Seguridad en todas las comunicaciones.

---

# Referencias

- [overview.md](./overview.md) — Vista general de arquitectura.
- [cross-cutting.md](./cross-cutting.md) — Componentes transversales.
- [../02-domain/domain-map.md](../02-domain/domain-map.md) — Contextos del dominio.
- [../03-product/modules.md](../03-product/modules.md) — Módulos funcionales.