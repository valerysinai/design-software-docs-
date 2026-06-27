# Ambientes del proyecto

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: DevOps

## Objetivo

Definir los ambientes utilizados durante el ciclo de vida del proyecto, especificando su propósito, las actividades permitidas y las reglas de uso para garantizar un proceso de desarrollo y despliegue controlado.

---

## Ambientes

| Ambiente | Propósito | Usuarios |
|----------|-----------|----------|
| Desarrollo | Construcción y pruebas locales de los microservicios | Desarrolladores |
| Integración | Validación de la comunicación entre servicios | Equipo de Desarrollo |
| Calidad | Pruebas funcionales, de integración y aceptación | Equipo de Calidad |
| Producción | Operación del sistema para usuarios finales | Usuarios finales |

---

## Desarrollo

Características:

- Desarrollo de nuevas funcionalidades.
- Pruebas unitarias.
- Ejecución mediante Docker Compose.
- Uso de datos de prueba.
- Cambios frecuentes.

---

## Integración

Características:

- Integración entre microservicios.
- Validación de APIs.
- Ejecución de pruebas de integración.
- Simulación de procesos completos.

---

## Calidad

Características:

- Validación funcional.
- Pruebas de aceptación.
- Verificación de requisitos.
- Evaluación del rendimiento básico.
- Corrección de incidencias antes del despliegue.

---

## Producción

Características:

- Plataforma disponible para usuarios finales.
- Alta disponibilidad.
- Monitoreo continuo.
- Registro de auditoría.
- Despliegue controlado mediante CI/CD.

---

## Flujo de despliegue

El proceso de promoción entre ambientes sigue el siguiente orden:

```text
Desarrollo
      │
      ▼
Integración
      │
      ▼
Calidad
      │
      ▼
Producción
```

Cada ambiente debe superar las validaciones establecidas antes de avanzar al siguiente.

---

## Configuración

Cada ambiente contará con:

- Variables de entorno propias.
- Bases de datos independientes.
- Configuración específica de seguridad.
- Recursos de infraestructura acordes con su propósito.

---

## Buenas prácticas

- No utilizar datos de producción en ambientes inferiores.
- Mantener configuraciones independientes por ambiente.
- Registrar cada despliegue realizado.
- Validar el funcionamiento de los servicios después de cada despliegue.
- Restringir el acceso al ambiente de producción al personal autorizado.

---

## Resultado esperado

La definición de ambientes garantiza un proceso de desarrollo, validación y despliegue organizado, reduciendo riesgos y asegurando la estabilidad de la plataforma durante todo su ciclo de vida.