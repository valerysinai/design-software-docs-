# Document Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **Document Service** administra los documentos generados por la plataforma, incluyendo reportes, actas, certificados y otros archivos relacionados con los procesos académicos.

---

## Responsabilidades

- Gestionar documentos.
- Almacenar archivos.
- Controlar versiones.
- Permitir consultas y descargas.
- Publicar eventos relacionados con documentos.

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

- Scheduling Service
- Academic Management Service

---

## Base de datos

El servicio administra una base de datos propia para almacenar la información de los documentos y sus versiones.

---

## Principios

- Base de datos independiente.
- Gestión centralizada de documentos.
- Comunicación mediante APIs REST y eventos.