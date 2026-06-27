# Mapa de Navegación

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir | Equipo: Por definir

## Objetivo

Describir la estructura de navegación de la plataforma y la relación entre sus principales módulos.

---

## Estructura general

```text
Inicio de sesión
        │
        ▼
Dashboard
        │
 ├── Usuarios
 ├── Programas
 ├── Fichas
 ├── Ambientes
 ├── Horarios
 ├── Reportes
 ├── Documentos
 ├── Auditoría
 └── Configuración
```

---

## Navegación

La navegación principal estará disponible mediante un menú lateral.

Cada módulo podrá acceder a:

- Consultar información.
- Crear registros.
- Editar registros.
- Eliminar registros cuando corresponda.

---

## Roles

La navegación dependerá del perfil del usuario:

- Administrador.
- Coordinador académico.
- Instructor.
- Aprendiz.
- Directivo.

Cada rol visualizará únicamente las opciones autorizadas.

---

## Buenas prácticas

- Menús consistentes.
- Máximo tres niveles de navegación.
- Breadcrumbs en pantallas internas.
- Acceso rápido a las funciones más utilizadas.