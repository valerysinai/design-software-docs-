# Auditoría y Trazabilidad

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Registrar de forma permanente las operaciones realizadas dentro del sistema para garantizar trazabilidad, seguimiento y cumplimiento de políticas institucionales.

---

## Registro de Auditoría

Representa la evidencia de una acción ejecutada sobre cualquier entidad del dominio.

### Atributos principales

- Identificador
- Fecha y hora
- Usuario
- Operación
- Entidad afectada
- Detalle

### Restricciones

- Los registros son inmutables.
- No pueden modificarse ni eliminarse.
- Deben conservarse según la política institucional de retención.

---

## Evento Auditado

Representa el cambio registrado durante una operación del sistema.

### Información registrada

- Evento.
- Usuario.
- Fecha.
- Resultado.
- Correlation ID.

---

## Reglas del contexto

- Toda operación relevante debe generar un registro de auditoría.
- La auditoría debe mantenerse independiente de los demás contextos.
- La información registrada debe permitir reconstruir cualquier operación realizada.