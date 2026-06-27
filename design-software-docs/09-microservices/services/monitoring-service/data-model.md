# Modelo de datos

> Estado: 🟡 En progreso | Última actualización: 2026-06-25

## Entidades principales

### Métrica

- id
- servicio
- nombre
- valor
- fechaRegistro

### Indicador

- id
- nombre
- descripción
- valorActual
- fechaCálculo

### Alerta

- id
- tipo
- descripción
- nivel
- fechaGeneración
- estado

---

## Relaciones

- Un servicio puede generar múltiples métricas.
- Un indicador se calcula a partir de una o varias métricas.
- Una alerta puede estar asociada a un indicador.

---

## Persistencia

El servicio mantiene una base de datos independiente siguiendo el patrón **Database per Service**.