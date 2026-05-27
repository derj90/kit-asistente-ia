# Empecemos — Léeme primero

Hola. Si estás leyendo esto, es porque ya descargaste el kit. Buena partida.

Antes de cualquier cosa: **respira**. No tienes que entender todo de inmediato. Este kit está armado para que la IA que abres en tu computador te lleve de la mano. Tu pega es decidir **qué** quieres automatizar; la pega técnica la hace ella.

## Lo que vas a hacer en los próximos 30 minutos

1. Leer este archivo hasta el final (5 min).
2. Completar `mi-perfil.md` (10 min). No te preocupes si tus respuestas no son perfectas; tu asistente IA te ayudará a refinarlas.
3. Abrir esta carpeta en **Codex** (codex.com), **Claude Code** o **Antigravity** (antigravity.com).
4. Escribirle al chat: **"Ayúdame a empezar"**.
5. A partir de ahí, dejas que la IA conduzca. Ella ya sabe qué hacer porque va a leer el archivo `AGENTS.md`.

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

Algunas tareas docentes incluyen información sensible (nombres y notas de estudiantes, RUTs, evaluaciones). **Nunca subas datos personales reales al kit ni los pongas en ejemplos**. Para probar tu bot, inventa nombres y datos (Juana Pérez, RUT 11.111.111-1, etc.). Cuando ya esté funcionando, lo usas con datos reales pero **fuera del kit**, en tu entorno habitual.

## Cuando termines

Cuando tu bot esté listo y la carpeta `mi-resultado/` completa, ya tienes:

- Un asistente funcional que resuelve una tarea concreta de tu trabajo.
- Un system prompt documentado que puedes reusar, compartir o iterar.
- Un par de pruebas que demuestran que el bot funciona.
- Una reflexión sobre lo que aprendiste construyéndolo.

Eso es todo. ¡Buen viaje!

— Equipo UDFV-UMCE.
