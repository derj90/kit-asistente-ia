# Empecemos — Léeme primero

Hola. Si estás leyendo esto, es porque ya descargaste el kit. Buena partida.

Antes de cualquier cosa: **respira**. No tienes que entender todo de inmediato. Este kit está armado para que la IA que abres en tu computador te lleve de la mano. Tu pega es decidir **qué** quieres automatizar; la pega técnica la hace ella.

## Lo que vas a hacer en los próximos 30 minutos

1. Abre esta carpeta en **Codex** (codex.com), **Claude Code** o **Antigravity** (antigravity.com).
2. En el chat, escríbele: **"Ayúdame a empezar"**.
3. La IA te va a guiar para completar `mi-perfil.md` con preguntas, una a la vez (toma ~10 min).
4. Una vez con el perfil listo, ella te propone el nivel de bot que te calza (1, 2, 3 o 4) y empiezan a construirlo.
5. Sigues lo que la IA te indique. Si te trabas, le dices "no entiendo" y baja el nivel.

## ¿Qué herramienta uso? Codex vs Claude Code vs Antigravity

Las tres sirven. Si no tienes preferencia:

- **Codex (app)** — La más amigable visualmente. Recomendada si nunca has usado un editor de código.
- **Antigravity** — Similar a Codex, también amigable. Buena opción.
- **Claude Code** — Más austera (corre en terminal), pero muy potente. Ideal si te sientes cómoda con la línea de comandos.

Si alguien te recomendó alguna en particular, ve por esa. Si no, **parte con Codex**.

## El flujo completo

```
1. Completas mi-perfil.md
   ↓
2. La IA te ayuda a elegir Nivel 1, 2 o 3-4
   ↓
3. Construyes tu bot iterando con la IA
   ↓
4. Pruebas tu bot con casos reales
   ↓
5. Llenas la carpeta mi-resultado/ (system prompt + reflexión + capturas)
```

## Los 3 niveles en una línea cada uno

- **Nivel 1 — Bot con personalidad** — "Quiero un asistente conversacional con buena personalidad para mi tarea X." → Construyes un **Gem** en gemini.google.com (más simple, sin OAuth).
- **Nivel 2 — Bot orquestador** — "Quiero que mi asistente actúe sobre Google Workspace por mí (Calendar, Drive, Gmail, Docs, Sheets)." → Necesitas configurar OAuth (te guiamos en `configuracion/02-google-workspace-oauth.md`).
- **Nivel 3-4 — Skill propia o conocimiento documental (RAG)** — "Quiero encapsular una rutina compleja en una skill reusable, O quiero un asistente que responda usando mis propios PDFs/documentos." → Skills o RAG.

Si dudas cuál te conviene, en `docs/cuando-usar-que.md` está la regla de oro. Y de todas formas tu asistente IA te ayudará a elegir cuando completes el perfil.

## Lo que NO necesitas

- **NO necesitas saber programar.** Si la IA te pide hacer algo técnico, ella misma te dice paso a paso qué tocar y dónde. Si te confundes, le dices "no entiendo" y baja el nivel.
- **NO necesitas pagar nada.** La API de Gemini tiene un plan gratuito que te alcanza de sobra. Codex y Antigravity tienen plan gratuito. Si te piden tarjeta de crédito en algún momento → **detente** y revisa que estés en la pantalla correcta.
- **NO necesitas instalar nada raro.** Solo el editor (Codex, Antigravity o Claude Code) y un navegador con sesión iniciada en una cuenta Google.

## Lo que SÍ necesitas tener listo

- Computador con conexión a internet.
- Cuenta Google activa.
- Una idea aproximada de **qué tarea repetitiva** quieres automatizar. Si no se te ocurre nada, en `mi-perfil.md` hay sugerencias.
- Algunas horas de tu tiempo, repartidas según el plazo que te hayas dado (o que tu formación te exija, si estás siguiendo un curso que enlaza este kit).

## Si te trabas

**Primera línea**: dile a tu asistente IA exactamente qué pasa. Es paciente, no se molesta, y va a desbloquearte. Pruebas frases como:
- "No entiendo qué es un system prompt."
- "Me perdí en el paso de OAuth. ¿Puedes repetirme desde el inicio?"
- "Mi bot está inventando datos que no existen. ¿Cómo lo arreglo?"

**Segunda línea**: revisa `docs/cuando-usar-que.md` y `docs/glosario-9-ladrillos.md`. Casi siempre la duda está ahí.

**Tercera línea**: si nada funciona, busca soporte humano en el espacio formativo correspondiente o escribe al equipo que te haya entregado este kit.

## Una nota sobre confidencialidad

Algunas tareas docentes incluyen información sensible (nombres y notas de estudiantes, RUTs, evaluaciones). Tu asistente IA va a detectar este tipo de información cuando aparezca y te va a preguntar si la dejas, la anonimizas o la sacas antes de publicar. **La decisión es tuya** — la IA solo te avisa para que no se te pase. Si prefieres probar con datos inventados (Juana Pérez, RUT 11.111.111-1, etc.) también funciona perfecto.

Lo único innegociable son las credenciales (API keys, contraseñas, tokens OAuth): esas nunca van al repo, no por privacidad tuya sino porque son secretos de tus proveedores (Google, OpenAI). Si una credencial real se cuela en un archivo que vas a subir, tu IA la saca antes.

## Cuando termines

Cuando tu bot esté listo y la carpeta `mi-resultado/` completa, ya tienes:

- Un asistente funcional que resuelve una tarea concreta de tu trabajo.
- Un system prompt documentado que puedes reusar, compartir o iterar.
- Un par de pruebas que demuestran que el bot funciona.
- Una reflexión sobre lo que aprendiste construyéndolo.

Eso es todo. ¡Buen viaje!

— Equipo UDFV-UMCE.
