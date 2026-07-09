# RCA — [Título del incidente]

| Campo | Valor |
|---|---|
| **Estado** | 🟡 En revisión / ✅ Cerrado / 🔴 Abierto |
| **Fecha del incidente** | YYYY-MM-DD HH:MM TZ |
| **Fecha de publicación** | YYYY-MM-DD |
| **Servicio / sistema** | Nombre del servicio, componente o flujo afectado |
| **Severidad** | Sev1 / Sev2 / Sev3 / Sev4 |
| **Impacto** | Descripción breve del impacto para usuarios, negocio o operaciones |
| **Autor** | @github-username |
| **Revisores** | @github-username, @github-username |
| **ID / ticket** | INC-1234 / LINK al ticket |

---

## Resumen ejecutivo

> Describe en 3-5 líneas qué ocurrió, cuánto tiempo duró, qué impacto tuvo y por qué se documenta este RCA.

*Ejemplo: El servicio de pagos experimentó un fallo de disponibilidad durante 42 minutos, afectando 18% de los pedidos. El incidente fue detectado por alertas de latencia y se resolvió al restaurar la conexión con el proveedor externo.*

---

## Impacto

### Usuarios / negocio
- Usuarios afectados:
- Funcionalidades afectadas:
- Pérdida de negocio o SLA:
- Riesgo de seguridad o cumplimiento:

### Operaciones / infraestructura
- Servicios impactados:
- Componentes involucrados:
- Duración total:
- Tiempo de detección:
- Tiempo de resolución:

---

## Cronología

| Hora | Evento |
|---|---|
| HH:MM | Detectado por alertas / reporte de usuario |
| HH:MM | Equipo asignado y se inicia la respuesta |
| HH:MM | Se identifica la causa y se implementa mitigación |
| HH:MM | Servicio recuperado y se valida estabilidad |

---

## Descripción del incidente

### Qué pasó
- Describe el comportamiento anómalo o la falla observada.

### Qué se esperaba que pasara
- Describe el comportamiento normal esperado.

### Señales / síntomas
- Alertas:
- Logs o métricas relevantes:
- Reportes de usuarios:

---

## Causa raíz

### Causa inmediata
- Qué falló directamente.

### Causa subyacente
- Qué condiciones o decisiones permitieron que el fallo ocurriera.

### Causa sistémica
- Problemas de proceso, documentación, herramientas, ownership o capacidad.

### Análisis de 5 Whys
1. Why 1: ...
2. Why 2: ...
3. Why 3: ...
4. Why 4: ...
5. Why 5: ...

---

## Factores contribuyentes

### Personas / procesos
- Falta de runbook actualizado:
- Falta de monitoreo o alertas insuficientes:
- Comunicación limitada durante el incidente:

### Tecnología / arquitectura
- Dependencia crítica no cubierta:
- Configuración inadecuada:
- Limitación de capacidad o escalabilidad:

### Operaciones
- Falta de automatización:
- Tiempo de recuperación largo:
- Ausencia de validación post-reparación:

---

## Acciones correctivas

### Inmediatas / ya ejecutadas
- [ ] ...
- [ ] ...

### Preventivas / pendientes
- [ ] ...
- [ ] ...
- [ ] ...

| Acción | Responsable | Fecha objetivo | Estado |
|---|---|---|---|
| Ejemplo: agregar alerta de latencia | @user | YYYY-MM-DD | Pendiente |

---

## Lecciones aprendidas

- Qué salió bien:
- Qué se puede mejorar:
- Qué cambios de proceso o cultura recomendar:

---

## Referencias

- Ticket / incident ID:
- PRs o cambios relacionados:
- Dashboards o métricas relevantes:
- Documentación operativa o runbooks:
