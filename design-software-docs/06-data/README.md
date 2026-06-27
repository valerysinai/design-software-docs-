# Datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Arquitectura / Base de Datos

## Contenido

Esta sección documenta la arquitectura de persistencia del sistema **Gestión de Horarios SENA**, incluyendo el modelo conceptual de datos, el diccionario de datos compartido y la estrategia de migración de esquemas.

Su objetivo es establecer una referencia común para la implementación de la capa de datos, manteniendo la independencia de cada microservicio y la consistencia del ecosistema.

---

## Alcance

En esta carpeta se documentan:

- Modelo conceptual de datos del sistema.
- Diccionario de datos compartido.
- Relaciones entre entidades.
- Estrategia de migración y versionado de esquemas.
- Convenciones generales para la persistencia.

---

## Relación con otras carpetas

> **Diferencia con `02-domain`:** allí se describen las entidades desde la perspectiva del negocio (reglas, comportamientos y lenguaje ubicuo). En esta carpeta se documenta su representación en la capa de persistencia.

> **Diferencia con `09-microservices`:** esta carpeta contiene únicamente el modelo de datos compartido del sistema. Los esquemas internos, tablas y estructuras específicas de cada microservicio deben documentarse dentro de `09-microservices/services/<servicio>/data-model.md`.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [data-dictionary.md](./data-dictionary.md) | Diccionario de datos compartido y definición de atributos principales | 🟡 |
| [models.md](./models.md) | Modelo conceptual de datos y relaciones entre entidades | 🟡 |
| [migration-strategy.md](./migration-strategy.md) | Estrategia para el versionado y migración de esquemas de base de datos | 🟡 |

---

## Principios

- Cada microservicio es propietario de su propia base de datos (**Database per Service**).
- No se permite el acceso directo a bases de datos de otros servicios.
- La integración entre servicios se realiza mediante APIs o eventos.
- Los modelos de datos compartidos deben mantenerse consistentes con el modelo de dominio.
- Toda modificación de esquemas debe realizarse mediante migraciones versionadas.