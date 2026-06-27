# Monitoring Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

El **Monitoring Service** recopila métricas operativas y de negocio para supervisar el estado de la plataforma, generar indicadores y emitir alertas cuando se detecten anomalías.

---

## Responsabilidades

- Monitorear el estado de los servicios.
- Gestionar indicadores (KPIs).
- Generar métricas operativas.
- Administrar alertas.
- Consolidar información para tableros de control.

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

El servicio administra una base de datos propia para almacenar métricas, indicadores y alertas generadas.

---

## Principios

- Base de datos independiente.
- Observabilidad centralizada.
- Comunicación mediante APIs REST y eventos.