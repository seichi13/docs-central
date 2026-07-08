# ADR-001 — [Título corto de la decisión]

| Campo | Valor |
|---|---|
| **Estado** | 🟡 Propuesto / ✅ Aceptado / ❌ Rechazado |
| **Fecha** | YYYY-MM-DD |
| **Autores** | @github-username |
| **Revisores** | @github-username, @github-username |

---

## Contexto

> ¿Cuál es el problema o situación que motiva esta decisión? Describe el estado actual y por qué se necesita tomar una decisión. Sé específico — menciona los servicios o componentes afectados.

*Ejemplo: Actualmente cada equipo gestiona su propia configuración de logging de forma inconsistente. Algunos usan console.log, otros Winston, otros Pino. Esto dificulta correlacionar logs en incidentes y aumenta el tiempo de diagnóstico.*

---

## Decisión

> La decisión tomada, en una o dos oraciones directas.

*Ejemplo: Adoptamos **Pino** como librería estándar de logging para todos los servicios Node.js.*

---

## Consecuencias

### ✅ Positivas
- ...
- ...

### ⚠️ Negativas / Trade-offs
- ...
- ...

### 📋 Acciones necesarias
- [ ] Migrar servicios existentes (deuda técnica, no bloqueante)
- [ ] Actualizar el template de nuevo servicio
- [ ] Documentar configuración estándar en guías

---

## Alternativas consideradas

### Alternativa 1: [Nombre]
**Por qué se descartó:** ...

### Alternativa 2: [Nombre]
**Por qué se descartó:** ...

---

## Referencias

- [Link a discusión en PR / Slack / donde ocurrió el debate]
- [Link a documentación relevante]
