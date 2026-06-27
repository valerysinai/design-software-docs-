# Gestión Académica

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir


> Contexto del dominio

## Propósito

Administrar la estructura académica que soporta el proceso formativo del SENA, incluyendo programas, fichas de formación, competencias y resultados de aprendizaje.

---

## Programa de Formación

Representa la estructura curricular oficial ofrecida por el SENA.

### Atributos principales

- Código
- Nombre
- Duración
- Nivel de formación

### Relaciones

- Contiene varias Competencias.
- Puede tener múltiples Fichas de Formación.

### Restricciones

- El código debe ser único.
- Todo programa debe tener al menos una competencia.

---

## Competencia

Representa un conjunto de conocimientos, habilidades y actitudes que desarrolla el aprendiz.

### Atributos principales

- Identificador
- Nombre
- Descripción
- Programa asociado

### Relaciones

- Pertenece a un Programa de Formación.
- Contiene uno o varios RAP.

### Restricciones

- No puede existir más de una competencia con el mismo nombre dentro del mismo programa.

---

## Resultado de Aprendizaje (RAP)

Representa la unidad mínima de aprendizaje dentro de una competencia.

### Atributos principales

- Identificador
- Descripción
- Competencia
- Evidencias asociadas

### Relaciones

- Pertenece a una Competencia.
- Puede desarrollarse en varias sesiones académicas.

### Restricciones

- Todo RAP debe pertenecer a una única competencia.

---

## Ficha de Formación

Representa el grupo de aprendices asociado a un programa durante un periodo académico.

### Atributos principales

- Código
- Programa
- Jornada
- Fecha de inicio
- Fecha de finalización
- Estado

### Estados

- Planeación
- Activa
- Finalizada
- Suspendida

### Relaciones

- Pertenece a un Programa de Formación.
- Agrupa Aprendices.
- Tiene uno o varios Instructores.
- Posee Horarios asociados.

### Restricciones

- Debe tener un coordinador responsable.
- Solo puede existir una ficha activa con el mismo código.

---

## Reglas del contexto

- Toda ficha pertenece a un único programa de formación.
- Toda competencia debe contener al menos un RAP.
- Los RAP desarrollados deben corresponder a las competencias del programa.
- Las modificaciones curriculares deben conservar trazabilidad.