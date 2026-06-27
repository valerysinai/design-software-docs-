# Training Environment Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **Training Environment Service** administra los ambientes de formación, su disponibilidad y los recursos físicos necesarios para la ejecución de las actividades académicas.

---

## Responsabilidades

- Gestionar ambientes de formación.
- Administrar recursos e inventario.
- Controlar la disponibilidad de ambientes.
- Gestionar bloqueos por mantenimiento.

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

- Reference Data Service
- Scheduling Service

---

## Base de datos

El servicio administra una base de datos propia para almacenar la información de ambientes, recursos y disponibilidad.

---

## Principios

- Base de datos independiente.
- Gestión centralizada de ambientes.
- Comunicación mediante APIs REST y eventos.