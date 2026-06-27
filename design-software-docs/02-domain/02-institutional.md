# Información Institucional

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Administrar la información institucional compartida utilizada por los diferentes módulos del Sistema de Gestión de Horarios del SENA.

---

## Regional

Representa una división administrativa del SENA.

### Atributos principales

- Identificador
- Nombre
- Ubicación

### Relaciones

- Agrupa uno o varios Centros de Formación.

### Restricciones

- El nombre debe ser único.

---

## Centro de Formación

Unidad organizacional donde se desarrollan los procesos de formación.

### Atributos principales

- Identificador
- Nombre
- Regional
- Dirección
- Información de contacto

### Relaciones

- Pertenece a una Regional.
- Contiene Ambientes de Formación.
- Gestiona Fichas de Formación.

### Restricciones

- No pueden existir centros duplicados dentro de una misma regional.

---

## Configuración Institucional

Almacena parámetros utilizados por distintos módulos del sistema.

### Atributos principales

- Clave
- Valor
- Tipo de dato
- Descripción

### Ejemplos

- Horarios institucionales.
- Capacidad máxima por ambiente.
- Parámetros de programación.
- Límites de ocupación.

### Restricciones

- Cada parámetro debe tener una clave única.
- Solo usuarios autorizados pueden modificar configuraciones.

---

## Reglas del contexto

- La información institucional es compartida por todos los contextos del dominio.
- Las modificaciones deben mantenerse auditadas.
- Los parámetros institucionales deben ser consistentes en toda la plataforma.