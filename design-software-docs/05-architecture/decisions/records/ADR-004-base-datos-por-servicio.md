# ADR-004: Base de datos por servicio

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir
> Equipo: Por definir

---

## Contexto

La plataforma **Gestión de Horarios SENA** está basada en una arquitectura de microservicios, donde cada dominio de negocio debe evolucionar de forma independiente.

El uso de una base de datos compartida entre servicios genera un alto acoplamiento, dificulta la evolución del modelo de datos y aumenta el riesgo de dependencias entre equipos de desarrollo.

Se requiere una estrategia que garantice la autonomía de cada servicio y facilite el despliegue independiente.

---

## Decisión

Se adopta el patrón **Database per Service**, mediante el cual cada microservicio será propietario exclusivo de su base de datos y de su modelo de persistencia.

Cada servicio será responsable de:

- Administrar su esquema de datos.
- Ejecutar sus propias migraciones.
- Controlar el acceso a su información.
- Exponer datos únicamente mediante APIs o eventos.

No estará permitido el acceso directo a la base de datos de otro servicio.

Cuando un servicio requiera información administrada por otro dominio, deberá obtenerla mediante APIs REST o eventos de dominio.

---

## Consecuencias

### Positivas

- Independencia entre servicios.
- Menor acoplamiento.
- Despliegues independientes.
- Evolución autónoma de los esquemas de datos.
- Mayor resiliencia de la arquitectura.

### Negativas / Trade-offs

- Consultas distribuidas más complejas.
- Posible duplicación controlada de información.
- Mayor complejidad para mantener consistencia entre servicios.

### Riesgos

- Consistencia eventual entre dominios.
- Incremento de la complejidad en reportes consolidados.
- Necesidad de diseñar correctamente las integraciones.

---

## Alternativas consideradas

| Alternativa | Motivo del descarte |
|-------------|---------------------|
| Base de datos compartida | Genera fuerte acoplamiento entre servicios y dificulta la evolución independiente. |
| Esquema compartido en una única base de datos | Mantiene dependencias entre dominios y aumenta el riesgo de afectar otros servicios durante cambios. |

---

## Impacto arquitectónico

### Componentes afectados

- Todos los microservicios.
- Bases de datos.
- APIs de integración.
- Message Broker.

### Servicios afectados

- IAM Service
- Academic Management Service
- Actors Service
- Training Environment Service
- Scheduling Service
- Reference Data Service
- Monitoring Service
- Document Service
- Audit Service

### Datos afectados

Cada servicio mantiene la propiedad exclusiva de sus entidades y de su modelo de persistencia.

La comunicación entre dominios se realizará únicamente mediante APIs o eventos.

---

## Estado de implementación

| Actividad | Estado |
|-----------|--------|
| Diseño | ☑ |
| Desarrollo | ☐ |
| Pruebas | ☐ |
| Producción | ☐ |

---

## Referencias

- [../overview.md](../overview.md) — Vista general de arquitectura.
- [../deployment.md](../deployment.md) — Arquitectura de despliegue.
- [../../06-data/database-per-service.md](../../06-data/database-per-service.md) — Estrategia de persistencia.
- [ADR-001-arquitectura-basada-en-microservicios.md](./ADR-001-arquitectura-basada-en-microservicios.md)