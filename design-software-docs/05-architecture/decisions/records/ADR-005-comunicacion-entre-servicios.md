# ADR-005: Comunicación entre servicios

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir
> Equipo: Arquitectura

---

## Contexto

La arquitectura del sistema **Gestión de Horarios SENA** está basada en microservicios independientes que deben intercambiar información para soportar procesos académicos, administrativos y operativos.

Existen operaciones que requieren una respuesta inmediata, como la autenticación o la consulta de información, mientras que otras pueden ejecutarse de forma asíncrona sin afectar la experiencia del usuario, como la generación de documentos, las notificaciones, el monitoreo y la auditoría.

Se requiere una estrategia de integración que reduzca el acoplamiento entre servicios, facilite la escalabilidad y mantenga la consistencia de la información.

---

## Decisión

Se adopta una estrategia híbrida para la comunicación entre microservicios:

- **APIs REST** para operaciones sincrónicas que requieren respuesta inmediata.
- **Eventos de dominio** para procesos asíncronos y desacoplados.

Las APIs REST serán utilizadas para consultas, validaciones y operaciones transaccionales.

Los eventos serán utilizados para propagar cambios relevantes entre servicios, permitiendo la actualización de información, la generación de auditorías, el monitoreo del sistema y el envío de notificaciones.

Eventos principales del dominio:

- UsuarioRegistrado
- UsuarioDesactivado
- FichaCreada
- InstructorAsignado
- HorarioProgramado
- ConflictoDetectado
- SesionFinalizada
- DocumentoGenerado

---

## Impacto arquitectónico

Esta decisión permite combinar la simplicidad de las APIs REST con la flexibilidad de una arquitectura orientada a eventos.

Los servicios mantienen un bajo acoplamiento, ya que no dependen directamente de las bases de datos ni de la implementación interna de otros dominios.

Toda comunicación deberá realizarse mediante contratos claramente definidos (API o eventos), evitando el acceso directo entre bases de datos de diferentes microservicios.

---

## Consecuencias

### Positivas

- Menor acoplamiento entre microservicios.
- Mayor escalabilidad de la plataforma.
- Mejor tolerancia a fallos.
- Integración flexible entre dominios.
- Facilita la auditoría y el monitoreo mediante eventos.

### Negativas / Trade-offs

- Incremento en la complejidad de la infraestructura.
- Necesidad de administrar un sistema de mensajería.
- Mayor esfuerzo para garantizar la consistencia eventual de los datos.

### Riesgos

- Pérdida de eventos si no existen mecanismos de persistencia o reintento.
- Duplicación temporal de información entre servicios.
- Mayor complejidad para depurar flujos distribuidos.

---

## Alternativas consideradas

| Alternativa | Por qué se descartó |
|-------------|---------------------|
| Solo APIs REST | Genera mayor acoplamiento temporal entre servicios y afecta la escalabilidad. |
| Solo eventos | No es adecuado para operaciones que requieren respuesta inmediata, como autenticación o consultas. |
| Base de datos compartida | Rompe la independencia de los microservicios y aumenta el acoplamiento entre dominios. |

---

## Referencias

- `../cross-cutting.md`
- `ADR-001-microservices-architecture.md`
- `ADR-004-database-per-service.md`
- `../../02-domain/events/README.md`