# Nombre del Servicio

> **Una línea describiendo qué hace este servicio y por qué existe.**

---

## 📋 Metadata

| Campo | Valor |
|---|---|
| **Owner** | @github-username |
| **Team** | Nombre del equipo |
| **Estado** | ✅ Activo |
| **Stack** | Node.js 20 / PostgreSQL / Redis |
| **Repo** | [github.com/tu-org/nombre-servicio](https://github.com) |
| **CI/CD** | [GitHub Actions](https://github.com) |
| **Logs** | [Link a Datadog / CloudWatch / etc] |
| **Alertas** | [Link a PagerDuty / Grafana / etc] |
| **Uptime** | [Link a status page] |

---

## 🏗️ Arquitectura

> Describe brevemente cómo funciona el servicio internamente y cómo encaja en el sistema.

```mermaid
graph LR
    A[Cliente / API Gateway] --> B[Este Servicio]
    B --> C[(PostgreSQL)]
    B --> D[(Redis Cache)]
    B --> E[Servicio Externo]
```

### Decisiones de diseño clave

- **¿Por qué esta base de datos?** Porque...
- **¿Por qué esta arquitectura?** Porque...

> Para decisiones mayores, ver [ADRs](../decisiones/index.md).

---

## 🔌 API

### Endpoints principales

=== "REST"

    ```
    GET  /api/v1/recursos          # Lista recursos
    POST /api/v1/recursos          # Crea un recurso
    GET  /api/v1/recursos/{id}     # Obtiene un recurso
    PUT  /api/v1/recursos/{id}     # Actualiza un recurso
    DELETE /api/v1/recursos/{id}   # Elimina un recurso
    ```

=== "Ejemplo de request"

    ```bash
    curl -X POST https://api.tuempresa.com/v1/recursos \
      -H "Authorization: Bearer $TOKEN" \
      -H "Content-Type: application/json" \
      -d '{"nombre": "ejemplo", "valor": 42}'
    ```

=== "Ejemplo de response"

    ```json
    {
      "id": "uuid-aqui",
      "nombre": "ejemplo",
      "valor": 42,
      "createdAt": "2026-01-01T00:00:00Z"
    }
    ```

### Eventos publicados (si aplica)

| Evento | Topic / Queue | Descripción |
|---|---|---|
| `recurso.creado` | `recursos-events` | Se emite cuando... |
| `recurso.eliminado` | `recursos-events` | Se emite cuando... |

---

## ⚙️ Runbook

### Setup local

```bash
# 1. Clonar e instalar dependencias
git clone https://github.com/tu-org/nombre-servicio
cd nombre-servicio
npm install

# 2. Configurar variables de entorno
cp .env.example .env
# Edita .env con los valores locales

# 3. Levantar dependencias
docker-compose up -d

# 4. Correr migraciones
npm run db:migrate

# 5. Iniciar
npm run dev
```

### Variables de entorno requeridas

| Variable | Descripción | Ejemplo |
|---|---|---|
| `DATABASE_URL` | Conexión a PostgreSQL | `postgresql://user:pass@localhost/db` |
| `REDIS_URL` | Conexión a Redis | `redis://localhost:6379` |
| `JWT_SECRET` | Secreto para tokens | *(ver Vault / Secrets Manager)* |

### Deploy

```bash
# El deploy es automático al mergear a main via GitHub Actions
# Para deploy manual de emergencia:
npm run build
npm run start:prod
```

### Respuesta a incidentes

!!! warning "Servicio no responde (5xx)"
    1. Revisar logs: [link a logs]
    2. Verificar conexión a base de datos: `npm run healthcheck`
    3. Reiniciar pod: `kubectl rollout restart deployment/nombre-servicio`
    4. Si persiste, escalar a @owner

!!! warning "Latencia alta"
    1. Revisar métricas de DB en [link a dashboard]
    2. Verificar queries lentos: [link a slow query log]
    3. Revisar uso de caché Redis

!!! danger "Corrupción de datos"
    1. **No reiniciar el servicio**
    2. Contactar inmediatamente a @owner
    3. Considerar modo mantenimiento

---

## 🔗 Dependencias

### Este servicio depende de:
- **Servicio B** — Para [qué propósito]
- **PostgreSQL** — Base de datos principal
- **Redis** — Caché de sesiones

### Otros servicios que dependen de este:
- **Servicio C** — Consume el endpoint `/api/v1/recursos`
- **Servicio D** — Escucha el evento `recurso.creado`

---

## 📝 Historial de cambios relevantes

| Fecha | Cambio | PR |
|---|---|---|
| 2026-07-01 | Migración a Node.js 20 | [#123](https://github.com) |
| 2026-05-15 | Agregado rate limiting | [#98](https://github.com) |
