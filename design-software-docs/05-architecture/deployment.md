# Arquitectura de Despliegue

> Estado: 🟢 Completo | Última actualización: 2026-06-22
> Autor: Por definir

## Ambientes

### Desarrollo

Utilizado para construcción y pruebas locales.

### Integración

Utilizado para pruebas de integración entre servicios.

### Calidad

Utilizado para validación funcional.

### Producción

Utilizado por usuarios finales.

---

## Componentes

### Frontend

Aplicación web responsable de la interacción con usuarios.

### API Gateway

Responsable de:

* Enrutamiento.
* Validación de JWT.
* Rate Limiting.
* Balanceo de carga.

### Microservicios

* IAM Service
* Academic Management Service
* Actors Service
* Training Environment Service
* Scheduling Service
* Reference Data Service
* Document Service
* Monitoring Service
* Audit Service

### Bases de Datos

Cada servicio administra su propia base de datos.

### Message Broker

Responsable de eventos asíncronos entre servicios.

### Sistema de Monitoreo

Responsable de métricas, logs y alertas.

---

## Diagrama Lógico

Usuario
↓
Frontend
↓
API Gateway
↓
Microservicios
↓
Bases de Datos

---

## Contenerización

Todos los servicios deberán desplegarse mediante contenedores Docker.

## Orquestación

Se recomienda Kubernetes para ambientes productivos.

## Escalabilidad

Los servicios podrán escalar horizontalmente de forma independiente según demanda.
