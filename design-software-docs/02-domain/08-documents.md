# Gestión Documental

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

> Contexto del dominio

## Propósito

Administrar la creación, almacenamiento y consulta de documentos generados durante la operación del sistema.

---

## Documento

Representa un archivo generado o almacenado por la plataforma.

### Atributos principales

- Identificador
- Tipo
- Nombre
- Fecha de generación
- Estado

### Relaciones

- Puede originarse a partir de una Plantilla.
- Puede asociarse a una Ficha, Sesión o Aprendiz.

### Restricciones

- Todo documento debe conservar su historial de versiones.

---

## Plantilla

Representa el modelo utilizado para generar documentos automáticamente.

### Tipos

- Acta.
- Reporte.
- Certificado.
- Constancia.

### Restricciones

- Solo puede existir una versión vigente por plantilla.

---

## Versión

Representa una modificación realizada sobre un documento.

### Atributos principales

- Número de versión.
- Fecha.
- Usuario responsable.

### Restricciones

- Las versiones anteriores no pueden eliminarse.

---

## Reglas del contexto

- Los documentos deben conservar trazabilidad durante todo su ciclo de vida.
- Toda modificación genera una nueva versión.
- La generación automática de documentos debe utilizar plantillas aprobadas.