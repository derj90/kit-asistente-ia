# Checklist de permisos — Qué necesitas según tu módulo

> Esta matriz te dice exactamente qué credenciales y permisos preparar antes de empezar a construir tu bot, según el camino que elegiste en `mi-perfil.md`.

---

## Módulo A — Bot con personalidad (Gem en gemini.google.com)

**Mínimo viable (recomendado para empezar)**:

- [x] Cuenta Google activa con sesión iniciada en https://gemini.google.com
- [ ] (Opcional) PDFs o documentos institucionales si quieres llenarle el campo "Knowledge" del Gem

**Si llevas el bot a Codex / Antigravity / Claude Code**:

- [ ] API key de Gemini (ver `01-gemini-api-key.md`)
- [ ] Archivo `credenciales.env` con `GEMINI_API_KEY=...`

**NO necesitas**:
- OAuth Google Cloud Console.
- Configurar APIs específicas en Google Cloud.

---

## Módulo B — Bot orquestador con Google Workspace

**Obligatorio**:

- [ ] Cuenta Google activa (decidida: personal o `@umce.cl`)
- [ ] API key de Gemini (ver `01-gemini-api-key.md`)
- [ ] OAuth Client ID + Secret en Google Cloud Console (ver `02-google-workspace-oauth.md`)
- [ ] APIs habilitadas según tus servicios (al menos una de: Calendar, Drive, Gmail, Docs, Sheets)
- [ ] Pantalla de consentimiento OAuth configurada
- [ ] Si estás en "modo prueba" (cuenta externa): tu propio correo agregado como **usuario de prueba**
- [ ] Archivo `credenciales.env` con `GEMINI_API_KEY`, `GOOGLE_OAUTH_CLIENT_ID`, `GOOGLE_OAUTH_CLIENT_SECRET`

**Scopes recomendados según caso**:

| Tu caso | Scope mínimo |
|---|---|
| Bot crea/edita eventos en Calendar | `auth/calendar` |
| Bot lee/crea archivos en Drive | `auth/drive.file` (solo archivos creados por la app) o `auth/drive` (todo) |
| Bot **lee** correos (clasifica, busca, resume) | `auth/gmail.readonly` |
| Bot **redacta borradores** de respuestas (recomendado) | `auth/gmail.compose` |
| Bot **envía** correos automáticamente (NO recomendado) | `auth/gmail.send` |
| Bot edita Google Docs | `auth/documents` |
| Bot edita Google Sheets | `auth/spreadsheets` |

**Política UDFV obligatoria**:
- [ ] Si tu bot va a tocar Gmail, no lo configures con `gmail.send` sin política de confirmación humana.
- [ ] Tu bot NUNCA debe enviar correos automáticamente sin revisión.
- [ ] Antes de borrar/modificar archivos en Drive, el bot debe pedir confirmación explícita.

---

## Módulo C.1 — Bot con skill propia

**Mínimo viable**:

- [ ] API key de Gemini (ver `01-gemini-api-key.md`)
- [ ] Archivo `credenciales.env` con `GEMINI_API_KEY=...`
- [ ] Codex o Antigravity instalado y con sesión iniciada
- [ ] Skill bien definida en `skills/[tu-skill].md`

**Si tu skill necesita conectarse a servicios externos**:

- [ ] OAuth Google Cloud Console (igual que Módulo B, según servicios)
- [ ] APIs habilitadas según los servicios que tu skill usa

---

## Módulo C.2 — Bot con conocimiento documental (RAG)

**Si lo haces en gemini.google.com como Gem**:

- [ ] Cuenta Google activa
- [ ] 2-3 PDFs o documentos relevantes para subir al campo "Knowledge" del Gem
- [ ] Documentos **anonimizados** si contenían datos sensibles

**Si lo haces en NotebookLM (recomendado para muchos documentos)**:

- [ ] Cuenta Google activa
- [ ] Acceso a https://notebooklm.google.com
- [ ] Documentos a subir (anonimizados)
- [ ] (Opcional) Compartir el cuaderno con tu equipo

**Si lo haces en Codex / Antigravity / Claude Code con la carpeta `memoria/`**:

- [ ] API key de Gemini
- [ ] Documentos en `memoria/` (anonimizados)
- [ ] `credenciales.env` con `GEMINI_API_KEY`

---

## Lista negra — Nunca jamás

Sin importar el módulo, estas cosas son línea roja:

- [ ] **NO** subas tu archivo `credenciales.env` a GitHub ni a ningún repo público.
- [ ] **NO** publiques capturas de pantalla que muestren tu API key o Client Secret.
- [ ] **NO** compartas tu API key por correo, WhatsApp ni Slack.
- [ ] **NO** uses datos personales sensibles de estudiantes (RUTs, notas, situaciones específicas) en ejemplos ni en `memoria/`.
- [ ] **NO** configures el bot para enviar correos automáticamente sin confirmación humana.
- [ ] **NO** le des al bot scopes que no necesita ("por si acaso"). Cada scope adicional es riesgo gratis.

---

## Si todo este listado te abruma

Es normal. Toma esto como guía de referencia, no como tarea. Tu asistente IA va a:

1. Leer `mi-perfil.md` para saber qué módulo elegiste.
2. Decirte exactamente qué necesitas configurar **para tu caso**, sin pedirte cosas innecesarias.
3. Acompañarte paso a paso por cada configuración cuando llegue el momento.

Tu pega no es entender este listado de memoria. Tu pega es decirle a tu IA "ayúdame a empezar" y dejarte guiar.
