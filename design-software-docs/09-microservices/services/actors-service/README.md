# Actors Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **Actors Service** administra la información de las personas que interactúan con la plataforma, como instructores, aprendices, coordinadores académicos y directivos.

---

## Responsabilidades

- Gestionar instructores.
- Gestionar aprendices.
- Gestionar coordinadores académicos.
- Gestionar directivos.
- Mantener la información de los actores institucionales.

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

---

## Base de datos

El servicio administra una base de datos propia para almacenar la información de los actores del sistema.

---

## Principios

- Base de datos independiente.
- Gestión centralizada de actores.
- Comunicación mediante APIs REST y eventos.