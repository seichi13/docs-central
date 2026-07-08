# Estándares del equipo

Acuerdos del equipo sobre cómo trabajamos. Si algo no está aquí, la decisión más reciente en un ADR tiene precedencia.

---

## Código

- **Lenguajes aprobados:** TypeScript (Node.js), Python. Cualquier otro requiere ADR.
- **Node.js LTS:** Siempre la versión LTS activa (hoy: v20).
- **Tests:** Cobertura mínima del 70% en lógica de negocio. No en controllers o adaptadores.
- **Linting:** ESLint / Ruff. El pipeline falla si hay errores.

## Git y PRs

- **Rama principal:** `main`. Siempre deployable.
- **Branches:** `feat/`, `fix/`, `docs/`, `chore/` + descripción corta.
- **PRs:** Mínimo 1 aprobación para merge a `main`. 2 para servicios críticos.
- **PRs grandes:** Si un PR tiene +500 líneas cambiadas, dividirlo.
- **Merge:** Squash merge. Un commit limpio por feature en `main`.

## Operación

- **On-call:** Rotación semanal. El owner del servicio es el primero en escalar.
- **Incidentes:** Todo incidente de producción tiene un postmortem breve (5 líneas mínimo) en el canal `#incidentes`.
- **Cambios en producción:** Solo via CI/CD. Sin cambios manuales directos.
- **Secretos:** Nunca en código ni en variables de entorno en texto plano. Usar Secrets Manager.

## Documentación

- **Cada servicio tiene:** `index.md`, `architecture.md`, `runbook.md`, `api.md`.
- **Docs desactualizadas:** Son bugs. Cualquiera puede (y debe) corregirlas via PR.
- **Decisiones de arquitectura:** Se registran como ADR en [`/decisiones`](../decisiones/index.md).

---

> Estos estándares se revisan cada 6 meses. Para proponer un cambio, abre un PR con la modificación y discútelo en el canal `#ingenieria`.
