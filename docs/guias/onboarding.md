# Onboarding — Bienvenido al equipo 👋

Esta guía te lleva de cero a funcional en tu primer día. Sigue los pasos en orden.

---

## Día 1 — Accesos y setup

### ✅ Checklist de accesos

Pídele a tu manager o buddy que te dé acceso a:

- [ ] GitHub — organización `tu-org`
- [ ] Slack — canales: `#ingenieria`, `#deploys`, `#incidentes`
- [ ] AWS / GCP / Azure — rol de lectura para empezar
- [ ] Datadog / herramienta de monitoreo
- [ ] Jira / Linear / gestor de tareas
- [ ] Password manager del equipo (1Password, etc.)
- [ ] VPN (si aplica)

### 🖥️ Setup de máquina

```bash
# Herramientas base requeridas
brew install node@20 python@3.12 docker git gh

# Configurar GitHub CLI
gh auth login

# Clonar el repo de docs (este mismo)
gh repo clone tu-org/docs-central
```

> Para setup específico de cada servicio, ver la sección [Servicios](../servicios/index.md) y el README de cada repo.

---

## Día 1-3 — Entender el sistema

### 🗺️ Lee esto en orden

1. [Mapa de servicios](../servicios/index.md) — entiende qué existe y para qué
2. Los READMEs de los 3-5 servicios más críticos del negocio
3. [Estándares del equipo](estandares.md) — cómo trabajamos

### 🤝 Personas clave

| Rol | Quién | Para qué consultarle |
|---|---|---|
| Tech Lead | @nombre | Decisiones de arquitectura |
| DevOps / Infra | @nombre | Accesos, CI/CD, infra |
| Tu buddy | @nombre | Cualquier duda del día a día |

---

## Semana 1 — Tu primer PR

El objetivo de tu primera semana es hacer un PR pequeño para familiarizarte con el flujo.

### Flujo de trabajo estándar

```bash
# 1. Crear rama desde main
git checkout main && git pull
git checkout -b feat/tu-nombre/descripcion-corta

# 2. Hacer cambios, commitear
git add .
git commit -m "feat: descripción corta del cambio"

# 3. Push y abrir PR
git push origin feat/tu-nombre/descripcion-corta
gh pr create --title "feat: descripción" --body "## Qué cambia\n..."
```

### Convención de commits

Usamos [Conventional Commits](https://www.conventionalcommits.org/):

| Prefijo | Cuándo usarlo |
|---|---|
| `feat:` | Nueva funcionalidad |
| `fix:` | Corrección de bug |
| `docs:` | Solo cambios de documentación |
| `refactor:` | Refactor sin cambio de comportamiento |
| `chore:` | Mantenimiento, dependencias |
| `test:` | Agregar o corregir tests |

---

## ❓ Preguntas frecuentes

**¿Dónde pregunto si tengo dudas técnicas?**
En `#ingenieria` en Slack. No hay preguntas tontas.

**¿Cómo sé quién es el owner de un servicio?**
En la página de cada servicio en este portal, o en el `catalog-info.yaml` del repo.

**¿Qué hago si encuentro algo roto o sin documentar?**
Abre un PR con la corrección. Todos somos dueños de la documentación.

**¿Hay algo que no deba hacer en producción?**
Ver [estándares del equipo](estandares.md).
