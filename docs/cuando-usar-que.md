# La regla de oro — Cuándo usar Gem, Antigravity, Codex o NotebookLM

> Decisión rápida sobre dónde construir tu bot según tu caso. Si estás dudando, parte por la opción más simple del listado.

---

## Resumen visual

| Tu caso | Herramienta sugerida |
|---|---|
| Bot conversacional simple, sin actuar sobre servicios externos | **Gem** (gemini.google.com) |
| Bot que debe actuar sobre Google Workspace | **Antigravity** o **Codex (app)** |
| Bot con habilidad propia compleja (skill) que se invoca | **Antigravity** o **Codex (app)** |
| Bot que responde citando muchos documentos propios | **NotebookLM** (notebooklm.google.com) |
| Bot con pocos documentos propios estables (calendario, reglamento) | **Gem** con campo Knowledge |
| Quiero todo en mi computador, sin depender de UI web | **Claude Code** (Terminal) |
| Quiero automatizar workflows que se ejecutan solos en background | **n8n** (n8n.udfv.cloud — solo material de referencia, no necesario para el entregable del curso) |

---

## Las 4 herramientas en detalle

### Gem en gemini.google.com

**Qué es**: un bot conversacional configurable dentro de la UI de Gemini. Le pegas un system prompt en "Instructions" y opcionalmente subes 2-3 documentos al campo "Knowledge".

**Cuándo conviene**:
- Es tu primera vez construyendo un bot.
- No tienes ganas de configurar API keys ni OAuth.
- Tu bot solo conversa (no necesita actuar sobre otros servicios).
- Tienes pocos documentos estables que el bot debe conocer.

**Limitaciones**:
- No puede leer correos, crear eventos ni manipular archivos.
- "Knowledge" tiene cupo limitado de documentos.
- Vive dentro de gemini.google.com (no en tu computador).

**Cuesta**: gratis con cuenta Google.

---

### Antigravity (antigravity.com) o Codex (codex.com)

**Qué son**: editores web/apps con un agente IA integrado que puede leer y modificar archivos de tu proyecto, invocar herramientas (Workspace, GitHub, bases de datos), y ejecutar código si hace falta. Son visualmente amigables.

**Cuándo conviene**:
- Tu bot debe actuar sobre Google Workspace (Calendar, Drive, Gmail).
- Tu bot tiene una skill compleja que requiere pasos definidos.
- Quieres que tu bot lea documentos de una carpeta `memoria/` en tu computador.
- Estás bien iniciando sesión y manteniendo el navegador abierto.

**Limitaciones**:
- Requieren API key Gemini y, para Workspace, OAuth Client en Google Cloud Console.
- Si tu conexión a internet es inestable, frustra.

**Cuesta**: plan gratuito generoso. Hay planes pagos para uso intensivo, pero el gratuito alcanza para todo el curso.

---

### NotebookLM (notebooklm.google.com)

**Qué es**: un sistema RAG de Google donde subes muchos documentos (PDFs, Docs, audios, videos transcritos, sitios web) a un cuaderno, y conversas con un asistente que responde citando los documentos por número.

**Cuándo conviene**:
- Tu bot vive sobre un corpus grande de documentos (decenas o cientos de páginas).
- Quieres que cada respuesta del bot **cite la fuente exacta**.
- Quieres que el bot pueda generar resúmenes, mapas conceptuales o "audio overview" del material.
- Tu rol implica responder consultas sobre normativa, syllabus o documentación institucional.

**Limitaciones**:
- El bot no actúa sobre Workspace (no envía correos ni crea eventos).
- No tiene skills propias programables.
- Es un sistema cerrado: no integra con flujos externos.

**Cuesta**: gratis con cuenta Google.

---

### Claude Code (Terminal)

**Qué es**: una IA agentic que corre en la línea de comandos de tu computador, sin UI gráfica. Lee y modifica archivos, invoca herramientas, ejecuta código.

**Cuándo conviene**:
- Te sientes cómoda con la Terminal.
- Quieres todo en tu computador sin depender de servicios web.
- Vas a hacer tareas más sofisticadas (scripts, integraciones múltiples).

**Limitaciones**:
- Curva de aprendizaje técnica más empinada.
- No es la opción más cálida para principiantes.

**Cuesta**: tiene plan gratuito (con límite de uso) y plan Pro.

---

## Diagrama de decisión

```
¿Mi bot necesita actuar sobre Google Workspace (Calendar/Drive/Gmail/Docs/Sheets)?
│
├── SÍ → Antigravity o Codex (app)
│
└── NO → ¿Mi bot debe responder citando muchos documentos propios?
       │
       ├── SÍ, decenas/cientos de páginas → NotebookLM
       │
       ├── SÍ, pero solo 2-3 documentos estables → Gem con Knowledge
       │
       └── NO, solo conversa → ¿Tengo tiempo / ganas de configurar API key?
              │
              ├── NO → Gem en gemini.google.com
              │
              └── SÍ → Antigravity / Codex / Claude Code (cualquiera sirve)
```

---

## Una recomendación honesta del equipo UDFV

Para el **entregable del Curso 2.4**, la mayoría de los participantes están mejor partiendo con un **Gem** en gemini.google.com. La razón: cero configuración técnica, resultado visible en 30 minutos, ruta clara hacia el entregable.

Si tu caso necesita Workspace o RAG, claro: ve a Antigravity / Codex / NotebookLM. Pero **no te compliques sin necesidad**. Un Gem bien hecho gana más puntos en la rúbrica que un orquestador a medio terminar.

---

## Una nota sobre n8n

n8n es la herramienta que se demostró en la sesión sincrónica. Sirve para construir **workflows automatizados** (procesos que se ejecutan solos en horarios definidos), no tanto para bots conversacionales.

Para el entregable del curso, **n8n no es necesario**. Quedaron las plantillas N1 a N5 en la instancia UDFV (n8n.udfv.cloud) como material de referencia para quienes quieran explorar más adelante. Pero no te exiges esa ruta para aprobar.
