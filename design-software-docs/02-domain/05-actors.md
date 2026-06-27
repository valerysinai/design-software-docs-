# Gestión de Actores

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Administrar la información de las personas y organizaciones que participan en el proceso de formación, garantizando la correcta asignación de responsabilidades durante la ejecución académica.

---

## Instructor

Representa al profesional encargado de orientar el proceso formativo y desarrollar las sesiones asignadas.

### Atributos principales

- Identificador
- Nombre completo
- Especialidad
- Disponibilidad
- Estado

### Relaciones

- Puede estar asignado a una o varias Fichas de Formación.
- Imparte una o varias Sesiones.
- Registra novedades durante la ejecución de la formación.

### Restricciones

- Debe tener al menos una especialidad registrada.
- Solo puede impartir competencias relacionadas con su perfil.
- No puede ser asignado a dos sesiones en la misma franja horaria.

---

## Aprendiz

Representa a la persona matriculada en un programa de formación del SENA.

### Atributos principales

- Identificador
- Documento
- Nombre completo
- Estado académico
- Ficha asociada

### Estados

- En formación
- Etapa productiva
- Egresado
- Retirado

### Relaciones

- Pertenece a una Ficha de Formación.
- Participa en múltiples Sesiones.
- Desarrolla Evidencias y Proyectos Formativos.

### Restricciones

- Solo puede pertenecer a una ficha activa.
- Debe estar matriculado para participar en las sesiones.

---

## Empresa

Representa la organización que recibe aprendices durante la etapa productiva.

### Atributos principales

- NIT
- Razón social
- Sector económico
- Dirección
- Contacto

### Relaciones

- Puede recibir varios Aprendices.
- Participa en procesos de etapa productiva.

### Restricciones

- El NIT debe ser único.

---

## Etapa Productiva

Representa el periodo de formación desarrollado en una empresa.

### Atributos principales

- Aprendiz
- Empresa
- Fecha de inicio
- Fecha de finalización
- Estado

### Restricciones

- Solo puede iniciarse cuando el aprendiz cumple los requisitos definidos por el programa.

---

## Reglas del contexto

- Todo instructor debe poseer competencias acordes con las actividades asignadas.
- Un aprendiz solo puede pertenecer a una ficha activa.
- La etapa productiva debe estar asociada a un aprendiz y una empresa válidos.