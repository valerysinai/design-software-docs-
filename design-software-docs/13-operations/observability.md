# Observabilidad

> Estado: 🟡 En progreso | Última actualización: 2026-06-26
> Autor: Por definir | Equipo: Por definir

## Objetivo

Establecer la estrategia de monitoreo para garantizar el correcto funcionamiento de la plataforma y detectar problemas de forma temprana.

---

## Componentes monitoreados

- API Gateway.
- Microservicios.
- Bases de datos.
- Message Broker.
- Contenedores.
- Infraestructura.

---

## Métricas principales

- Uso de CPU.
- Uso de memoria.
- Espacio en disco.
- Tiempo de respuesta.
- Cantidad de solicitudes.
- Errores HTTP.
- Disponibilidad del servicio.

---

## Logs

Todos los servicios deberán generar:

- Logs estructurados.
- Registro de errores.
- Eventos de negocio.
- Auditoría.

---

## Trazabilidad

Las solicitudes deberán incluir un **Correlation ID** para facilitar el seguimiento entre microservicios.

---

## Alertas

Se recomienda generar alertas cuando:

- Un servicio deje de responder.
- El uso de CPU supere el 80%.
- La memoria supere el 80%.
- Existan errores repetitivos.
- Se detecten fallos en la comunicación entre servicios.

---

## Tableros

Los paneles de monitoreo deberán mostrar:

- Estado de los servicios.
- Disponibilidad.
- Consumo de recursos.
- Eventos críticos.
- Tendencias históricas.