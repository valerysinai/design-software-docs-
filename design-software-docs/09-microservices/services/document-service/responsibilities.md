# Responsabilidades del Document Service

> Estado: 🟡 En progreso | Última actualización: 2026-06-26

## Objetivo

Administrar el almacenamiento y consulta de documentos generados por la plataforma.

---

## Responsabilidades

- Registrar documentos.
- Actualizar versiones.
- Permitir consultas.
- Gestionar descargas.
- Publicar eventos relacionados con documentos.

---

## Límites del servicio

Este servicio no administra:

- Usuarios.
- Horarios.
- Ambientes.
- Programas de formación.
- Auditoría.

---

## Servicios relacionados

| Servicio | Relación |
|----------|----------|
| Scheduling Service | Genera reportes de horarios |
| Academic Management Service | Genera documentos académicos |
| Audit Service | Registra operaciones sobre documentos |