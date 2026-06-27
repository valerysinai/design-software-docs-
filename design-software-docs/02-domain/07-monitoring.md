# Seguimiento y Monitoreo

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Supervisar el comportamiento operativo del sistema mediante indicadores, alertas y notificaciones que apoyen la toma de decisiones y permitan identificar desviaciones en la ejecución de los procesos académicos.

---

## Indicador (KPI)

Representa una métrica utilizada para evaluar el desempeño de la operación.

### Atributos principales

- Identificador
- Nombre
- Descripción
- Valor actual
- Umbral

### Ejemplos

- Ocupación de ambientes.
- Carga horaria de instructores.
- Horarios ejecutados.
- Conflictos detectados.

---

## Alerta

Representa una notificación generada cuando un indicador supera un umbral definido.

### Atributos principales

- Identificador
- Tipo
- Prioridad
- Fecha
- Estado

### Restricciones

- Debe generarse automáticamente.
- Debe asociarse al indicador que la originó.

---

## Notificación

Representa una comunicación enviada a uno o varios usuarios.

### Canales

- Correo electrónico.
- Notificación interna.
- Mensajería institucional.

### Restricciones

- Solo usuarios autorizados reciben información sensible.

---

## Dashboard

Representa la consolidación visual de indicadores para los diferentes perfiles del sistema.

### Información presentada

- Indicadores.
- Alertas activas.
- Estado de la programación.
- Estadísticas de utilización.

---

## Reglas del contexto

- Los indicadores deben actualizarse periódicamente.
- Las alertas se generan automáticamente cuando se supera un umbral.
- Toda notificación debe quedar registrada para efectos de trazabilidad.