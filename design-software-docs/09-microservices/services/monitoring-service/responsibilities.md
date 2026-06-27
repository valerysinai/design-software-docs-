# Responsabilidades del Monitoring Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Objetivo

Supervisar el funcionamiento de la plataforma mediante la recopilación de métricas e indicadores que apoyen la operación y la toma de decisiones.

---

## Responsabilidades

- Recopilar métricas de los servicios.
- Calcular indicadores de desempeño.
- Generar alertas operativas.
- Publicar eventos relacionados con el monitoreo.

---

## Límites del servicio

Este servicio no administra:

- Usuarios.
- Horarios.
- Ambientes.
- Programas de formación.
- Documentos.

---

## Servicios relacionados

| Servicio | Relación |
|----------|----------|
| Todos los microservicios | Envían métricas y eventos |
| Audit Service | Registra eventos de monitoreo |