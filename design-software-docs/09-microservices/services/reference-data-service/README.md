# Reference Data Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir 

## Objetivo

El **Reference Data Service** administra la información institucional compartida utilizada por los diferentes microservicios del sistema.

---

## Responsabilidades

- Gestionar regionales.
- Gestionar centros de formación.
- Administrar catálogos.
- Gestionar parámetros institucionales.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [responsibilities.md](./responsibilities.md) | Funciones del servicio | 🟡 |
| [api-contract.md](./api-contract.md) | Contratos de la API | 🟡 |
| [data-model.md](./data-model.md) | Modelo de datos | 🟡 |
| [events.md](./events.md) | Eventos publicados y consumidos | 🟡 |

---

## Dependencias

- Academic Management Service
- Scheduling Service
- Training Environment Service

---

## Base de datos

El servicio administra su propia base de datos para almacenar información institucional y parámetros compartidos.

---

## Principios

- Base de datos independiente.
- Información reutilizable.
- Comunicación mediante APIs REST y eventos.