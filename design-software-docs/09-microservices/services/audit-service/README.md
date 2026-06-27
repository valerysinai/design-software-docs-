# Audit Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Arquitectura

## Objetivo

El **Audit Service** registra y almacena los eventos generados por los diferentes microservicios para garantizar la trazabilidad, el cumplimiento y el seguimiento de las operaciones realizadas en la plataforma.

---

## Responsabilidades

- Registrar eventos de auditoría.
- Almacenar registros históricos.
- Consultar trazabilidad de operaciones.
- Mantener la integridad de los registros.
- Proporcionar información para auditorías institucionales.

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

- Todos los microservicios de la plataforma.

---

## Base de datos

El servicio administra una base de datos propia para almacenar los registros de auditoría de forma independiente.

---

## Principios

- Base de datos independiente.
- Registro centralizado de auditoría.
- Comunicación mediante APIs REST y eventos.