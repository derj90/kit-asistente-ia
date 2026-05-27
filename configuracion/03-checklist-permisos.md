# Checklist de permisos — Qué necesitas según tu nivel

> Esta matriz te dice exactamente qué credenciales y permisos preparar antes de empezar a construir tu bot, según el camino que elegiste en `mi-perfil.md`.

---

## Nivel 1 — Bot con personalidad (Gem en gemini.google.com)

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

## Nivel 2 — Bot orquestador con Google Workspace

**Obligatorio**:

- [ ] Cuenta Google activa (decidida: personal o institucional)
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

**Reglas operativas innegociables**:
- [ ] Si tu bot va a tocar Gmail, no lo configures con `gmail.send` sin política de confirmación humana.
- [ ] Tu bot no envía correos automáticamente sin revisión humana. Esto es regla operativa, no opcional.
- [ ] Antes de borrar/modificar archivos en Drive, el bot debe pedir confirmación explícita.

---

## Nivel 3 — Bot con skill propia

**Mínimo viable**:

- [ ] API key de Gemini (ver `01-gemini-api-key.md`)
- [ ] Archivo `credenciales.env` con `GEMINI_API_KEY=...`
- [ ] Codex o Antigravity instalado y con sesión iniciada
- [ ] Skill bien definida en `skills/[tu-skill].md`

**Si tu skill necesita conectarse a servicios externos**:

- [ ] OAuth Google Cloud Console (igual que Nivel 2, según servicios)
- [ ] APIs habilitadas según los servicios que tu skill usa

---

## Nivel 4 — Bot con conocimiento documental (RAG)

**Si lo haces en gemini.google.com como Gem**:

- [ ] Cuenta Google activa
- [ ] 2-3 PDFs o documentos relevantes para subir al campo "Knowledge" del Gem
- [ ] Tu asistente IA te avisa antes de subir si detecta datos que conviene revisar; tú decides si anonimizas o subes tal cual

**Si lo haces en NotebookLM (recomendado para muchos documentos)**:

- [ ] Cuenta Google activa
- [ ] Acceso a https://notebooklm.google.com
- [ ] Documentos listos para subir (tu IA revisa contigo si hay algo identificable que prefieras anonimizar)
- [ ] (Opcional) Compartir el cuaderno con tu equipo

**Si lo haces en Codex / Antigravity / Claude Code con la carpeta `memoria/`**:

- [ ] API key de Gemini
- [ ] Documentos en `memoria/` (tu IA te avisa si conviene anonimizar algo antes de usarlo como fuente)
- [ ] `credenciales.env` con `GEMINI_API_KEY`

---

## Lo innegociable — credenciales y envío automático

Casi todo en este kit es decisión tuya: qué documentos subes, qué nombres dejas en las capturas, qué datos usas en ejemplos. Tu asistente IA te avisa cuando detecte algo que conviene revisar, pero la decisión es tuya.

Hay dos excepciones que sí son reglas duras, no decisión del participante:

**1. Credenciales reales (API keys, OAuth tokens, contraseñas) NO se suben al repo nunca.**
Esto no es paternalismo — son secretos del proveedor (Google, OpenAI, etc.) y exponerlos compromete la seguridad de todas las cuentas asociadas. Si tu IA detecta una credencial real en un archivo, la saca antes de commitear.

- [ ] No subas tu archivo `credenciales.env` a GitHub ni a ningún repo público.
- [ ] No publiques capturas de pantalla que muestren tu API key o Client Secret.
- [ ] No compartas tu API key por correo, WhatsApp ni Slack.

**2. El bot NO envía correos automáticamente sin revisión humana.**
Esto es regla operativa, no de privacidad: cualquier acción del bot sobre Gmail queda como borrador hasta que tú confirmes.

- [ ] No configures el bot con `gmail.send` sin política explícita de confirmación.
- [ ] No le des al bot scopes que no necesita ("por si acaso"). Cada scope adicional es riesgo gratis.

**Lo demás** (qué documentos pones en `memoria/`, qué nombres aparecen en tus ejemplos, qué muestran tus capturas) lo decides tú con la ayuda de tu asistente IA, que te avisa y te ofrece anonimizar si quieres.

---

## Si todo este listado te abruma

Es normal. Toma esto como guía de referencia, no como tarea. Tu asistente IA va a:

1. Leer `mi-perfil.md` para saber qué nivel elegiste.
2. Decirte exactamente qué necesitas configurar **para tu caso**, sin pedirte cosas innecesarias.
3. Acompañarte paso a paso por cada configuración cuando llegue el momento.

Tu pega no es entender este listado de memoria. Tu pega es decirle a tu IA "ayúdame a empezar" y dejarte guiar.
