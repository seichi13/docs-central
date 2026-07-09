# ADR-002 — [Lista de Espera de NCE]

| Campo | Valor |
|---|---|
| **Estado** | ✅ Aceptado  |
| **Fecha** | 2026-07-08 |
| **Autores** | @seichi13 |
| **Revisores** | @cvargasn, @ralf-winet |

---

## Contexto


Actualmente la Lista de espera consta de 2 procesos
- Un cron que se ejecuta cada 3 minutos, llama al NCE `network-elements` para obtener el listado de OLTs y luego llama a `query-gponontautofind` con el nombre de cada OLT y guarda la información en REDIS (dentro de un nodo worker).
- Una api que busca la información de OLT en REDIS en base a un serial number(ONT) con el objetivo de poder obtener las vlans asociadas a dicha OLT y se pueda realizar la activación

Los problemas son:
- Durante la sincronización que realiza el cron, genera una indisponibilidad de la lista de espera de 30 segundos (se optimizó luego a 10 segundos), por ende genera errores en la activación.
- Se realizan muchas llamadas al NCE (1 para el listado de OLTs y una para el listado de ONTs por cada OLT) estimando 150 OLTs, se harían 151 llamadas cada 3 minutos; más de 3000 llamadas por hora
---

## Decisión

Se opta por llamar al NCE `network-elements` cada 3 horas y guardar la información en REDIS; luego, en cada activación llamar al NCE `query-gponontautofind` y luego ir a REDIS para obtener la información de la OLT.

---

## Consecuencias

### ✅ Positivas
- No se tienen tiempos muertos en cada sincronización por lo que no tendríamos errores en Activación.
- Se reduce considerablemente las llamadas al NCE Domain.

### ⚠️ Negativas / Trade-offs
- Una llamada adicional por cada Activación

### 📋 Acciones necesarias
- [ ] Modificar servicios existentes (no bloqueante)
- [ ] Hacer pruebas en ambiente bajo
- [ ] Desplegar en producción

---

## Alternativas consideradas

### Alternativa 1: [Nombre]
- Llamar en línea al NCE `query-gponontautofind` y luego al NCE `network-elements` en cada Activación.

**Por qué se descartó:** Se descarta porque el equipo de Redes indica que la información de OLTs no cambia mucho en el día y podríamos tenerla cacheada.


---

## Referencias

- Documentación de Huawei entregada por Redes, aunque no tiene detalle de parámetros opcionales o requeridos nos permitió ver que podíamos llamar a `query-gponontautofind` con el serial number de una ONT parameter: 'ontsn'
