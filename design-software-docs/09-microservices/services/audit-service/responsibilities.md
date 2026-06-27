# Responsabilidades del Audit Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Objetivo

Registrar las operaciones realizadas por los diferentes microservicios para garantizar la trazabilidad y el cumplimiento de las políticas institucionales.

---

## Responsabilidades

- Registrar eventos de auditoría.
- Almacenar operaciones históricas.
- Consultar registros.
- Mantener la integridad de la información.
- Publicar eventos cuando sea necesario.

---

## Límites del servicio

Este servicio no administra:

- Usuarios.
- Programas de formación.
- Horarios.
- Ambientes.
- Documentos.

---

## Servicios relacionados

| Servicio | Relación |
|----------|----------|
| Todos los microservicios | Publican eventos auditables |
| Monitoring Service | Consulta información para indicadores |