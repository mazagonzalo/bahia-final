# Bahía — Instrucciones del proyecto (Claude Code)

Proyecto del equipo para **Bahía Social Sports Club** (club deportivo-social premium en Bahía de
Banderas, Nayarit). Trabajamos **dos personas en paralelo**, cada quien en su propia máquina y su
propia sesión de Claude. Este archivo es la fuente de verdad de **cómo trabajamos juntos**.

> **El repo es el cerebro compartido.** La conversación de Claude NO se comparte entre máquinas; lo
> que sincroniza el contexto entre nosotros es **git**: archivos versionados que ambos Claudes leen.

---

## 🧠 Memoria compartida — los 3 archivos que importan

| Archivo | Qué es |
|---|---|
| `docs/STATUS.md` | **Estado vivo.** La foto de "dónde vamos hoy". Se sobreescribe siempre. **Léelo primero.** |
| `docs/handoffs/AAAA-MM-DD-<nombre>.md` | **Bitácora por sesión.** Un archivo por persona por día. Nunca se borra. Es la memoria/historial. |
| `docs/decisions.md` | Decisiones importantes + el porqué (1 línea c/u). |

Los **entregables** (docs de estrategia, investigación de mercado, etc.) viven en `docs/estrategia/`.

---

## ▶️ Al INICIAR cada sesión (protocolo obligatorio)

1. Lee `docs/STATUS.md`.
2. Lee los **2-3 handoffs más recientes** de `docs/handoffs/`.
3. Resume al usuario dónde quedó el proyecto y cuál es su siguiente paso.

Atajo: el usuario puede correr **`/catchup`** (hace esto + `git pull --rebase` + `git log`).
Un hook de SessionStart (en `.claude/settings.json`) ya inyecta el STATUS y el último handoff al abrir.

## ⏹️ Al TERMINAR cada sesión (protocolo obligatorio)

Corre el flujo de **`/handoff`**:
1. Escribe `docs/handoffs/<fecha>-<nombre>.md` (plantilla en `docs/handoffs/_TEMPLATE.md`).
2. Actualiza **solo el bloque del usuario** en `docs/STATUS.md`.
3. Muestra el handoff para aprobación, luego `git commit` + `git push`.

El handoff SIEMPRE responde 6 cosas: **Qué hice · Por qué · Estado actual (qué corre / qué falla) ·
Siguiente paso · Archivos tocados · Bloqueos/dudas para el otro.**

---

## 🌿 Workflow de git (dos personas)

- **Nadie commitea a `main` directo.** `main` = estable. `dev` = integración.
- Trabajo: rama desde `dev` → `git checkout dev && git pull --rebase && git checkout -b feat/<algo>`.
- **`git pull --rebase` antes de empezar** y antes de tocar archivos compartidos.
- Commits chicos, push seguido. Para integrar: **PR a `dev`** (`gh pr create --base dev`); el cuerpo del PR ES un handoff.
- Mensaje de commit: `tipo(quién): resumen [fecha]` — ej. `handoff(xavier): pivote day-pass [2026-06-15]`.

### Reglas anti-conflicto (importantes)
- **Handoffs = 1 archivo por persona por día** (nombre único `AAAA-MM-DD-<nombre>.md`) → nunca chocan.
- **`STATUS.md` tiene un bloque por persona** (`## Xavier`, `## <Cuate>`) → cada quien edita SOLO el suyo.
- Si dos van a tocar el **mismo archivo** (la web, el deck), coordínenlo en `STATUS.md` antes.

---

## 📦 Qué hay en el repo

- `presentacion-agentes-bahia.html` — deck de presentación al cliente.
- `bahia-sitio.html` — mock del sitio de marketing.
- `comparacion-sistema-actual-vs-ia.html` — comparativo.
- `bahiaclub-briefing/` — briefing de marca, brandbook, fotos, planes.
- `docs/estrategia/` — entregables de estrategia e investigación (ver `docs/STATUS.md`).
- `assets/`, `css/`, `js/` — recursos de la web.

---

## Reglas generales

- Haz lo que se pidió; ni más ni menos. Lee un archivo antes de editarlo.
- NO crees archivos de documentación nuevos salvo que se pidan.
- NUNCA subas secretos, credenciales o `.env`.
- `git commit`/`push` solo cuando el usuario lo pida; nunca a `main` directo.
