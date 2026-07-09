# ADR-001 — [Distancia para búsqueda de Cajas]

| Campo | Valor |
|---|---|
| **Estado** | ✅ Aceptado  |
| **Fecha** | 2026-07-01 |
| **Autores** | @seichi13 |
| **Revisores** | @cvargasn, @ralf-winet |

---

## Contexto

El proceso de catastro toma el valor de la constante llamada `RADIO_CAJAS` cuando la tabla `config.p_parametro_cobertura` no tiene datos en el campo num_distancia_caja. Actualmente el valor es de 500 mientras que la tabla tiene el valor 200.
Se necesita homologar a 200 el valor porque se identificó que al ejecutarse el proceso con un rango de 500 metros se carga mucha información en la tabla `red.t_direccion_caja` lo que provoca una caída de Base de Datos; la tabla llega a tener un peso de más de 65GB y un select simple se cuelga.

---

## Decisión

Se modifica el valor por defecto a 200, de manera que si la tabla no tiene valor o el usuario de base de datos no tiene acceso, el proceso de catastro se ejecute con un radio de 200 metros.

---

## Consecuencias

### ✅ Positivas
- Ante un cambio de usuario de base de datos o una modificación en base de datos, el proceso de catastro se continua ejecutando sin problemas.
- Se reduce el riesgo de una ejecución con un radio muy amplio.

### ⚠️ Negativas / Trade-offs
- Ninguna

### 📋 Acciones necesarias
- [ ] Modificar código existente (no bloqueante)
- [ ] Desplegar en producción

---

## Alternativas consideradas

### Alternativa 1: [Nombre]
- Dejar el valor por defecto en 500 como se denifió inicialmente.

**Por qué se descartó:** Si se llega a ejecutar el proceso con 500 metros se tumbaría todo el flujo de activación.


---

