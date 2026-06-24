# Mapa de dependencia

> Estado: 🟢 Completo | Última actualización: 2026-06-23
> Autor: Por definir | Equipo: Por definir


## Objetivo

Visualizar las dependencias funcionales entre microservicios.

## Dependencias Principales

```text
                    ┌─────────────────────┐
                    │  IAM SERVICE        │
                    └─────────┬───────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────┐
│                API GATEWAY / BFF                    │
└─────────────────────────────────────────────────────┘

        ▼                ▼                 ▼

 Academic Service    Actors Service    Environment Service
        │                 │                 │
        └──────────┬──────┴──────────┬──────┘
                   ▼
           Scheduling Service
                   │
          ┌────────┴────────┐
          ▼                 ▼

 Document Service   Monitoring Service

                   ▼

             Audit Service