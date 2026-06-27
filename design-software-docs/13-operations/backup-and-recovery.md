# Respaldo y recuperación

> Estado: 🟡 En progreso | Última actualización: 2026-06-25
> Autor: Por definir | Equipo: Por definir

## Objetivo

Definir la estrategia de respaldo y recuperación para garantizar la continuidad del servicio y minimizar la pérdida de información.

---

## Respaldo

Se recomienda realizar:

- Backups completos.
- Backups incrementales.
- Copias automáticas programadas.
- Almacenamiento seguro de respaldos.

---

## Frecuencia

| Tipo | Frecuencia |
|------|------------|
| Base de datos | Diario |
| Configuración | Semanal |
| Documentos | Diario |

---

## Recuperación

En caso de incidente se debe:

1. Identificar el problema.
2. Restaurar el respaldo más reciente.
3. Validar la integridad de la información.
4. Restablecer los servicios.
5. Confirmar la operación normal.

---

## Objetivos

| Indicador | Valor |
|-----------|-------|
| RTO | 4 horas |
| RPO | 30 minutos |

---

## Pruebas

Periódicamente se recomienda realizar simulaciones de recuperación para verificar la efectividad del proceso y garantizar la disponibilidad de los respaldos.

---

## Buenas prácticas

- Cifrar los respaldos.
- Mantener múltiples copias.
- Almacenar copias fuera del servidor principal.
- Verificar periódicamente la restauración.
- Documentar cada procedimiento realizado.