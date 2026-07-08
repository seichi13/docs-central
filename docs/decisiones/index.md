# Decisiones de Arquitectura (ADR)

Un ADR (Architecture Decision Record) documenta una decisión técnica importante: **qué se decidió, por qué, y qué alternativas se descartaron**.

No documentar las decisiones es la principal causa de que el equipo repita los mismos debates cada 6 meses.

---

## Registro

| # | Título | Estado | Fecha |
|---|---|---|---|
| [ADR-001](adr-001-template.md) | Template de ejemplo | 📄 Template | — |
| *(tu primera decisión real va aquí)* | | | |

### Estados posibles

| Estado | Significado |
|---|---|
| 🟡 Propuesto | En discusión, no aceptado aún |
| ✅ Aceptado | Decisión tomada y vigente |
| ❌ Rechazado | Se evaluó y no se adoptó |
| 🔄 Deprecado | Fue válido, ya no aplica |
| ↪️ Reemplazado | Sustituido por otro ADR |

---

## ¿Cuándo escribir un ADR?

Escribe un ADR cuando:

- Eliges una nueva tecnología, framework o herramienta
- Cambias la arquitectura de un servicio de forma significativa
- Estableces un patrón que esperan que otros sigan
- Descartas una alternativa aparentemente obvia (para que nadie la proponga de nuevo)

**No hace falta** para decisiones de implementación de bajo nivel o refactors sin impacto en interfaces externas.
