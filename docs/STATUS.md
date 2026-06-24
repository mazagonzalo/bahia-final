# STATUS — Bahía (estado vivo)

> Para ponerte al día: lee esto + los 2 handoffs más recientes en `docs/handoffs/`.
> **Actualizado: 2026-06-23 (Gonzalo)**

## En una línea
Pivotamos la oferta a Bahía: **ya no construimos un sistema completo ni reemplazamos su software
(Trainingym), sino que somos la CAPA COMPANION** — inteligencia + administración + crecimiento — encima
de lo que ya tienen. **Objetivo #1 = Motor de Conversión Day Pass → Inscripción.**

## La propuesta en 30 segundos
- El dueño ya usa **Trainingym** (gestión de gym: socios, cobros, acceso, app, rutinas, NPS). No lo
  reemplazamos; lo exprimimos al 100%.
- **3 pilares:** A) aprovechamiento Trainingym + copiloto interno del staff · B) inteligencia &
  administración (dashboard del consejo + CFO IA + BI) · C) crecimiento (marketing IG/FB + concierge
  WhatsApp <5 min + Day Pass).
- **Cobro:** retainer mensual (A+B) **$35-55k MXN** + **8% del ingreso nuevo** (C). Piloto de 2-3 meses
  con criterio numérico.
- **Visión larga (interna):** la capa companion es un producto replicable para otros clubes/gyms que
  ya usan Trainingym/Playtomic. Bahía = caso de éxito #1.

## Entregables (en `docs/estrategia/`, abrir en navegador)
1. `01-analisis-vs-commerce-os-template.html` — qué reutilizar del template Commerce-OS.
2. `02-pivote-estrategia-companion.html` — el pivote (no reemplazar, acompañar).
3. `03-propuesta-v3-investigacion-mercado.html` — **propuesta v3 + investigación de mercado completa** (cifras verificadas).
4. `04-motor-daypass-objetivo-1.html` — **el objetivo #1 a detalle** (embudo de 8 etapas, BI, dependencias, economía, piloto).

## En progreso

### Xavier
- **Trabajando en:** Fase 2 Prisma (DATABASE_URL ya en Vercel — desbloqueado).
- **Siguiente:** schema Prisma → Fase 3 harness → Fase 4 dashboard+CRM → Fase 5 UI por agente.
- **Agente asignado:** **Reactivación de Miembros** — socios que pagan pero no vienen (detectado vía Trainingym cuando esté integrado). No arrancar hasta Fase 6 (datos Trainingym disponibles).

### Gonzalo
- **Hecho (2026-06-23):** mejoré 6 agentes con **memoria/entrenamiento** (Tendencias, Secretaria, Eventos, Seguimiento, Crítico, Contenido) + tema Bahía Deep en el dashboard. Todo en `main` (producción), CI verde, 0 PRs abiertos. Cerré el ciclo de mejoras **sin conexiones externas**.
- **Entregable:** `comparativo-evolucion-propuesta.html` — plan de mkt de Bahía mejorado, módulo por módulo.
- **Siguiente:** poner `LINKFOXAGENT_API_KEY` en Vercel (Google Trends sale 0 sin ella); conectar canales (WhatsApp/Meta/Google); meter Ventas en **Instagram + Messenger** (integración nueva, camino técnico en memoria).

## Decisiones recientes (ver `docs/decisions.md`)
- NO reemplazar Trainingym → ser capa companion.
- Objetivo #1 = Day Pass → Inscripción (ingreso nuevo, atribuible, prueba el BI).
- Geografía correcta: **Bahía de Banderas, Nayarit** (metro Vallarta–Riviera Nayarit).

## Pendientes / bloqueos (requieren al dueño)
- Auditoría real de Trainingym (con login): ¿qué exporta? ¿API?
- ¿Usa Playtomic? ¿cuánta demanda le trae?
- Accesos: Meta (IG/FB) + WhatsApp Business API.
- Reglas del Day Pass: precio temporada alta/baja, qué incluye, ventana de acreditación.
- **Agente de Reputación:** `GOOGLE_BUSINESS_ACCOUNT_ID` + `GOOGLE_BUSINESS_LOCATION_ID` + acceso OAuth a Google Business Profile API (para leer y responder reseñas de Google Maps).
- **Agente de Contenido (skills visuales):** `HUMANIZERAI_API_KEY` (detect-ai) + `CANVA_ACCESS_TOKEN` (OAuth cuenta Bahía en Canva).
- **Fotos del club:** imágenes reales de cada instalación para onboarding de `club_assets` (canal a definir: WhatsApp al agente vs Google Drive).
- **Plano actualizado del club:** el actual es de 2024; la cancha de fútbol ya es 8 pádel + 8 pickleball.
