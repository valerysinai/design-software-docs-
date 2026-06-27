# Guía de diseño de APIs

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Definir las convenciones para el diseño, implementación y evolución de las APIs REST utilizadas por los microservicios del sistema **Gestión de Horarios SENA**.

Estas guías buscan mantener consistencia entre servicios, facilitar la integración y mejorar la mantenibilidad de la plataforma.

---

# Principios generales

Las APIs del sistema deberán cumplir los siguientes principios:

- Arquitectura REST.
- Comunicación mediante HTTPS.
- Formato de intercambio JSON.
- Recursos identificados mediante URI.
- Operaciones sin estado (Stateless).
- Compatibilidad entre versiones.

---

# Convención de URLs

Las rutas utilizarán nombres en plural y en minúsculas.

## Ejemplos

```text
/api/v1/users
/api/v1/instructors
/api/v1/schedules
/api/v1/environments
/api/v1/programs
```

No se utilizarán verbos en las rutas.

Correcto:

```text
GET /api/v1/users
POST /api/v1/users
```

Incorrecto:

```text
POST /createUser
GET /getSchedules
```

---

# Métodos HTTP

| Método | Uso |
|---------|-----|
| GET | Consultar información |
| POST | Crear recursos |
| PUT | Actualizar completamente un recurso |
| PATCH | Actualizar parcialmente un recurso |
| DELETE | Eliminar o desactivar un recurso |

---

# Códigos de respuesta

| Código | Significado |
|---------|-------------|
| 200 | Operación exitosa |
| 201 | Recurso creado |
| 204 | Operación sin contenido |
| 400 | Solicitud inválida |
| 401 | No autenticado |
| 403 | Acceso denegado |
| 404 | Recurso no encontrado |
| 409 | Conflicto de negocio |
| 500 | Error interno del servidor |

---

# Formato de respuesta

## Respuesta exitosa

```json
{
  "success": true,
  "data": {
    "id": "SCH-001",
    "status": "CONFIRMED"
  }
}
```

---

## Respuesta con error

```json
{
  "success": false,
  "error": {
    "code": "SCH-409",
    "message": "El instructor ya tiene un horario asignado en esa franja."
  }
}
```

---

# Versionado

Las APIs deberán versionarse mediante la URL.

Ejemplo:

```text
/api/v1/schedules
```

Una nueva versión deberá publicarse únicamente cuando existan cambios incompatibles con versiones anteriores.

---

# Paginación

Las operaciones de consulta que retornen listas deberán soportar paginación.

Parámetros recomendados:

```text
?page=1
&size=20
```

Ejemplo:

```text
GET /api/v1/schedules?page=1&size=20
```

---

# Filtrado y ordenamiento

Las consultas podrán utilizar filtros mediante parámetros de la URL.

Ejemplos:

```text
GET /api/v1/schedules?status=CONFIRMED

GET /api/v1/instructors?centerId=10

GET /api/v1/environments?type=LABORATORY
```

Para ordenar resultados:

```text
?sort=name,asc
```

---

# Buenas prácticas

- Utilizar nombres consistentes para los recursos.
- Evitar exponer detalles internos de la base de datos.
- Mantener compatibilidad con versiones existentes.
- Documentar todas las APIs mediante OpenAPI.
- Validar todas las entradas antes de procesarlas.
- Utilizar códigos HTTP de forma consistente.
- Registrar las operaciones críticas para auditoría.

---

# Relación con la arquitectura

Las APIs forman parte de la estrategia de comunicación definida en la arquitectura de microservicios.

Las operaciones síncronas se implementan mediante APIs REST, mientras que la comunicación asíncrona se realiza mediante eventos de dominio documentados en **02-domain**.

---

# Referencias

- `../05-architecture/overview.md`
- `../05-architecture/cross-cutting.md`
- `../02-domain/domain-events.md`