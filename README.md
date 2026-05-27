# Kit del Curso 2.4 — Automatizaciones con IA en el proceso docente

**Unidad de Desarrollo y Formación Virtual (UDFV) — Universidad Metropolitana de Ciencias de la Educación (UMCE)**

Plantilla de proyecto para que los participantes del **Curso 2.4 del Plan de Formación en Competencias Digitales 2026-1S** construyan su primer asistente con IA aplicado a su práctica docente o administrativa, acompañados por un asistente técnico automático (Codex, Claude Code o Antigravity) que lee el archivo `AGENTS.md` y los guía paso a paso.

## ¿A quién va dirigido este kit?

- Docentes UMCE (cualquier facultad, cualquier nivel) que hayan inscrito el Curso 2.4.
- Profesionales y administrativos UMCE que automatizan procesos repetitivos.
- En general: cualquier persona del ecosistema UMCE que quiera dejar de hacer manualmente tareas que la IA puede ayudar a resolver.

**No necesitas saber programar.** El kit está pensado para que la IA haga el trabajo técnico mientras tú decides qué automatizar y por qué.

## ¿Qué incluye?

- `AGENTS.md` — Instrucciones que **Codex, Claude Code o Antigravity** leen automáticamente al abrir esta carpeta. Define cómo tu asistente técnico debe trabajar contigo.
- `INICIO-AQUI.md` — La guía cálida y paso a paso para ti. Pártela leyendo esto.
- `mi-perfil.md` — Plantilla breve para que tu asistente sepa quién eres y qué quieres construir.
- Carpetas `agentes/`, `skills/`, `memoria/`, `configuracion/`, `conversaciones/`, `entregable/` — Cada una con plantillas y ejemplos listos para adaptar.
- `docs/` — Material de apoyo: glosario de los 9 ladrillos, regla de oro para elegir herramienta, ética y rúbrica resumida.

## Cómo usarlo (3 opciones)

### Opción 1 — La más simple (recomendada)

1. En la página de este repo en GitHub, haz clic en el botón verde **"Use this template"** → **"Create a new repository"**.
2. Ponle un nombre a tu copia (por ejemplo `mi-asistente-redaccion`) y créala.
3. Descárgala a tu computador (botón **"Code"** → **"Download ZIP"**, o si usas git: `git clone`).
4. Abre la carpeta descargada en **Codex** (codex.com) o **Antigravity** (antigravity.com).
5. Escribe en el chat: **"Ayúdame a empezar"**. La IA leerá `AGENTS.md` y te guiará desde ahí.

### Opción 2 — Descargar ZIP directamente

1. Botón verde **"Code"** → **"Download ZIP"**.
2. Descomprime en tu computador.
3. Abre la carpeta en Codex o Antigravity. Continúa desde el paso 4 de la Opción 1.

### Opción 3 — Si conoces git y GitHub CLI

```bash
gh repo create mi-asistente --template derj90/curso-2.4-automatizaciones-ia-kit --public --clone
cd mi-asistente
# abre en tu editor de IA
```

## ¿Qué vas a construir?

El curso te pide elegir **uno** de tres caminos:

- **Módulo A — Bot con personalidad**: un asistente conversacional con instrucciones claras (system prompt). Se construye en Gemini Gems o equivalente. Es el más simple, ideal si nunca has hecho esto.
- **Módulo B — Bot orquestador**: un agente que decide qué herramienta de Google Workspace usar (Calendar, Drive, Gmail, Docs, Sheets) según lo que le pidas. Requiere configurar OAuth.
- **Módulo C — Bot con habilidad propia o conocimiento documental**: una skill encapsulada (rutina reusable) o un bot RAG que responde citando tus propios documentos.

No hace falta que decidas ahora — al abrir el kit en tu asistente IA, te ayudará a elegir según tu perfil.

## Plazos del curso

| Grupo | Fecha de cierre |
|---|---|
| Grupo 1 | Domingo 7 de junio de 2026 (23:59 hrs) |
| Grupo 2 | Domingo 2 de agosto de 2026 (23:59 hrs) |

Aprobación: nota ≥ 4,0 sobre 7,0 en la rúbrica oficial (ver `docs/rubrica-resumen.md`).

## Material complementario

- **Curso virtual completo**: https://umce.online/autoformacion/automatizaciones-ia
- **Aula virtual UMCE**: link en tu correo institucional + en el portal del curso.
- **Soporte humano**: equipo UDFV vía correo `udfv@umce.cl`.

## Licencia

Este kit se distribuye bajo licencia **Creative Commons Atribución-CompartirIgual 4.0 (CC BY-SA 4.0)**. Puedes adaptarlo, mejorarlo y redistribuirlo siempre que cites a la UDFV-UMCE y mantengas la misma licencia. Ver `LICENSE`.

## Créditos

Producido por la **Unidad de Desarrollo y Formación Virtual (UDFV)** de la Universidad Metropolitana de Ciencias de la Educación, en el marco del Plan de Formación en Competencias Digitales para Docentes UMCE, año 2026-1S.

Coordinación: David Reyes Jiménez · UDFV · UMCE.
