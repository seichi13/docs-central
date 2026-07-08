# Cómo crear un nuevo servicio

Antes de crear un servicio nuevo, confirma con el Tech Lead que no existe ya algo que resuelva la necesidad.

---

## Checklist de creación

### 1. Crear el repositorio

```bash
# Usa el template estándar (ajusta el nombre)
gh repo create tu-org/nombre-servicio \
  --template tu-org/service-template \
  --private
```

Si no existe un template todavía, usa la estructura mínima:

```
nombre-servicio/
├── src/
├── tests/
├── docs/
│   ├── index.md          ← copia de docs/servicios/servicio-a.md
│   ├── architecture.md
│   ├── runbook.md
│   └── api.md
├── .github/
│   ├── workflows/
│   └── pull_request_template.md
├── .env.example
├── Dockerfile
└── README.md
```

### 2. Documentar antes de codear

Llena al menos estas secciones del template de docs **antes** de escribir código:

- [ ] Metadata (owner, stack, estado)
- [ ] Descripción de una línea
- [ ] Diagrama de arquitectura borrador
- [ ] Dependencias conocidas

Esto fuerza claridad en el diseño y facilita el review del equipo.

### 3. Agregar al catálogo

Agrega el servicio a este portal en [`docs/servicios/index.md`](../servicios/index.md) con su link y owner.

### 4. Configurar CI mínimo

El pipeline mínimo debe incluir:

- [ ] Lint + tests en cada PR
- [ ] Build de imagen Docker
- [ ] Deploy automático a staging en merge a `main`
- [ ] Deploy a producción con aprobación manual

### 5. Configurar alertas antes de ir a producción

- [ ] Healthcheck endpoint (`GET /health`)
- [ ] Alerta de error rate > 1%
- [ ] Alerta de latencia p99 > umbral definido
- [ ] Runbook linkado desde la alerta

---

!!! tip "Regla de oro"
    Si un servicio llega a producción sin runbook, el primer que tenga que operar ese servicio en un incidente va a sufrir. Ese alguien probablemente seas tú.
