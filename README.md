# docs-central

Portal de documentación técnica interna. Construido con [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).

🌐 **Ver documentación:** https://seichi13.github.io/docs-central

---

## Setup local

```bash
# Instalar dependencias
pip install -r requirements.txt

# Servidor local con hot-reload
mkdocs serve

# Abre http://localhost:8000
```

## Estructura

```
docs/
├── index.md              # Home con mapa de servicios
├── servicios/            # Un archivo por microservicio
│   └── servicio-a.md     # Template: copia y renombra para cada servicio
├── guias/                # Onboarding, estándares, how-tos
└── decisiones/           # Architecture Decision Records (ADRs)
```

## Cómo contribuir

1. Edita cualquier archivo `.md` en `docs/`
2. Abre un PR — el checklist del PR template incluye documentación
3. Al mergear a `main`, GitHub Actions publica automáticamente

> El botón ✏️ en cada página del portal abre directamente el editor de GitHub.

## Deploy

Automático vía GitHub Actions al hacer push a `main`. Ver `.github/workflows/deploy-docs.yml`.

Requiere que GitHub Pages esté habilitado en el repositorio apuntando a la rama `gh-pages`.

--- 

## Objectives

- Standardize software delivery.
- Improve software quality.
- Reduce duplicated CI/CD logic.
- Centralize engineering documentation.
- Automate releases.
- Improve security.
- Enable Platform Engineering.

## Repository Structure

```
.github/
docs/
templates/
scripts/
```

## Standards

- Git Strategy
- Semantic Versioning
- Conventional Commits
- Pull Request Standards
- Branch Protection
- Release Process
- API Standards
- Security Standards

## CI/CD

Reusable GitHub Workflows are located under:

```
.github/workflows/
```

## Maintainers

Software Architecture Team