# Kit UDFV — Tu primer asistente con IA

> Una carpeta lista para abrir en **Codex** (app) o **Antigravity** y construir tu asistente paso a paso, guiado por la IA.

**Mantenido por**: Unidad de Desarrollo y Formación Virtual (UDFV) — Universidad Metropolitana de Ciencias de la Educación (UMCE).

---

## ¿A quién va dirigido?

- Docentes, profesionales y equipos universitarios que quieren dejar de hacer manualmente tareas repetitivas y delegárselas a un asistente con IA.
- Personas sin background técnico: no necesitas saber programar.
- Equipos de unidades académicas o administrativas que quieren un punto de partida común para experimentar con IA aplicada a su trabajo.

El kit es independiente: no requiere estar inscrito en ningún curso. Si tu formación lo enlaza, mejor — pero también sirve por sí solo para construir tu primer asistente.

---

## ¿Qué construyes con este kit?

Tres niveles posibles, según tu necesidad y tu comodidad técnica:

- **Nivel 1 — Bot con personalidad**: un asistente conversacional con instrucciones claras (system prompt sólido). Se construye en Gemini Gems o equivalente. Es el más simple, ideal si nunca has hecho esto.
- **Nivel 2 — Bot orquestador**: un agente que decide qué herramienta de Google Workspace usar (Calendar, Drive, Gmail, Docs, Sheets) según lo que le pidas. Requiere configurar OAuth.
- **Nivel 3-4 — Bot con skill propia o conocimiento documental**: una skill encapsulada (rutina reusable) o un bot RAG que responde citando tus propios documentos.

No hace falta que decidas ahora — al abrir el kit en tu asistente IA, te ayudará a elegir según tu perfil.

---

## ¿Qué incluye el kit?

- `AGENTS.md` — Instrucciones que **Codex, Antigravity o Claude Code** leen automáticamente al abrir esta carpeta. Define cómo tu asistente técnico debe trabajar contigo.
- `INICIO-AQUI.md` — La guía cálida y paso a paso para ti. Pártela leyendo esto.
- `mi-perfil.md` — Plantilla breve para que tu asistente sepa quién eres y qué quieres construir.
- Carpetas `agentes/`, `skills/`, `memoria/`, `configuracion/`, `conversaciones/`, `mi-resultado/` — Cada una con plantillas y ejemplos listos para adaptar.
- `docs/` — Material de apoyo: glosario de los 9 ladrillos, regla de oro para elegir herramienta, ética y límites del uso de IA.

---

## Cómo se usa (3 opciones)

### Opción 1 — La más simple (recomendada)

1. En la página de este repo en GitHub, haz clic en el botón verde **"Use this template"** → **"Create a new repository"**.
2. Ponle un nombre a tu copia (por ejemplo `mi-asistente-redaccion`) y créala.
3. Descárgala a tu computador (botón **"Code"** → **"Download ZIP"**, o si usas git: `git clone`).
4. Abre la carpeta descargada en **Codex** (codex.com) o **Antigravity** (antigravity.com).
5. Completa `mi-perfil.md` (10 minutos).
6. Escribe en el chat: **"Ayúdame a empezar"**. La IA leerá `AGENTS.md` y te guiará desde ahí.

### Opción 2 — Descargar ZIP directamente

1. Botón verde **"Code"** → **"Download ZIP"**.
2. Descomprime en tu computador.
3. Abre la carpeta en Codex o Antigravity. Continúa desde el paso 4 de la Opción 1.

### Opción 3 — Si conoces git y GitHub CLI

```bash
gh repo create mi-asistente --template derj90/kit-asistente-ia --public --clone
cd mi-asistente
# abre en tu editor de IA
```

---

## Lo que NO necesitas

- **NO necesitas saber programar.** Si la IA te pide hacer algo técnico, ella misma te dice paso a paso qué tocar y dónde.
- **NO necesitas pagar nada.** La API de Gemini tiene un plan gratuito que alcanza de sobra. Codex y Antigravity también tienen plan gratuito.
- **NO necesitas instalar nada raro.** Solo el editor (Codex o Antigravity) y un navegador con sesión iniciada en una cuenta Google.

---

## Mantenido por

Unidad de Desarrollo y Formación Virtual (UDFV) · Universidad Metropolitana de Ciencias de la Educación · Chile.

Portal UDFV: https://umce.online

---

## Licencia

Este kit se distribuye bajo licencia **Creative Commons Atribución-CompartirIgual 4.0 (CC BY-SA 4.0)**. Puedes adaptarlo, mejorarlo y redistribuirlo siempre que cites a la UDFV-UMCE y mantengas la misma licencia. Ver `LICENSE`.

---

## Créditos

Producido por la **Unidad de Desarrollo y Formación Virtual (UDFV)** de la Universidad Metropolitana de Ciencias de la Educación.

Coordinación: David Reyes Jiménez · UDFV · UMCE.
