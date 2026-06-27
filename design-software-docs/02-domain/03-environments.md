# Gestión de Ambientes

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Administrar los ambientes de formación y los recursos físicos necesarios para el desarrollo de las actividades académicas, garantizando su disponibilidad y uso adecuado durante la programación de horarios.

---

## Ambiente de Formación

Representa el espacio físico donde se desarrollan las sesiones de formación.

### Atributos principales

- Identificador
- Nombre
- Tipo
- Capacidad
- Centro de Formación

### Tipos de ambiente

- Aula
- Laboratorio
- Taller
- Sala especializada

### Relaciones

- Pertenece a un Centro de Formación.
- Puede tener varios recursos asociados.
- Puede ser utilizado por múltiples horarios en diferentes franjas.

### Restricciones

- La capacidad debe ser mayor que cero.
- El nombre debe ser único dentro del mismo centro.
- No puede utilizarse simultáneamente en dos sesiones.

---

## Recurso

Representa un elemento físico disponible dentro de un ambiente.

### Atributos principales

- Identificador
- Nombre
- Cantidad
- Estado
- Ambiente asociado

### Ejemplos

- Equipos de cómputo
- Proyectores
- Herramientas
- Mobiliario
- Equipos especializados

### Restricciones

- La cantidad disponible no puede ser negativa.
- Todo recurso pertenece a un único ambiente.

---

## Disponibilidad

Representa los periodos en los cuales un ambiente puede utilizarse.

### Atributos principales

- Ambiente
- Día
- Hora inicio
- Hora fin
- Estado

### Restricciones

- Debe respetar mantenimientos y bloqueos registrados.
- No pueden existir franjas superpuestas para el mismo ambiente.

---

## Reglas del contexto

- Un ambiente solo puede estar asignado a una sesión por franja horaria.
- La capacidad del ambiente debe ser suficiente para la cantidad de aprendices.
- Las reservas respetan la disponibilidad registrada.
- Los recursos del ambiente deben encontrarse disponibles durante la sesión.