# Academic Management Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **Academic Management Service** administra la información académica del sistema, incluyendo programas de formación, competencias, resultados de aprendizaje (RAP) y fichas de formación.

---

## Responsabilidades

- Gestionar programas de formación.
- Administrar competencias.
- Gestionar resultados de aprendizaje (RAP).
- Administrar fichas de formación.

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
- Actors Service

---

## Base de datos

El servicio administra una base de datos propia para almacenar toda la información académica.

---

## Principios

- Base de datos independiente.
- Gestión centralizada de la información académica.
- Comunicación mediante APIs REST y eventos.