# Carpeta `configuracion/`

Aquí están las guías para configurar las **credenciales y permisos** que tu bot necesita según el módulo que elijas.

## Qué incluye

- `01-gemini-api-key.md` — Cómo obtener una API key gratuita de Gemini (Google AI Studio). Necesaria para Módulos A, B y C si tu herramienta lo requiere.
- `02-google-workspace-oauth.md` — Cómo configurar OAuth en Google Cloud Console para que tu bot pueda actuar sobre Calendar, Drive, Gmail, Docs, Sheets. **Solo necesario para Módulo B.**
- `03-checklist-permisos.md` — Matriz "qué permisos necesitas según módulo elegido".
- `credenciales-EJEMPLO.env` — Plantilla del archivo donde guardarás tus credenciales reales (copia este archivo como `credenciales.env`, sin la palabra EJEMPLO, y complétalo).

## Importante sobre credenciales

**Nunca subas el archivo `credenciales.env` con valores reales a GitHub o a ningún repositorio público.** El `.gitignore` de este kit ya está configurado para ignorarlo, pero igual revisa antes de commitear cualquier cosa.

Si por accidente publicas una credencial:
1. Vuelve al panel donde la generaste y **revócala** (Google AI Studio → revocar key; Google Cloud Console → eliminar OAuth client).
2. Genera una credencial nueva.
3. Avisa a tu instructora o al equipo UDFV.

## Resumen rápido por módulo

| Módulo | Necesitas API key Gemini | Necesitas OAuth Google | Necesitas archivo `.env` |
|---|---|---|---|
| **A — Gem en gemini.google.com** | No (basta con la sesión web) | No | No |
| **A — Bot en Codex/Antigravity** | Sí (gratuito en AI Studio) | No | Sí |
| **B — Orquestador con Workspace** | Sí | Sí | Sí |
| **C.1 — Skill propia** | Sí | Depende del caso | Sí |
| **C.2 — RAG con documentos propios** | Sí | Depende del caso | Sí |

> Si vas por Módulo A construyendo el Gem directamente en gemini.google.com (la ruta más simple), **no necesitas configurar nada técnico** — solo iniciar sesión en tu cuenta Google. Salta esta carpeta y ve directo a `agentes/`.
