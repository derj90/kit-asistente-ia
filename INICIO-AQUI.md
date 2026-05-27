# Empecemos — Léeme primero

Hola. Si estás leyendo esto, es porque ya descargaste el kit del Curso 2.4. Buena partida.

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

Si tu colega del curso te recomendó alguna, ve por esa. Si no, **parte con Codex**.

## El flujo completo del curso

```
1. Completas mi-perfil.md
   ↓
2. La IA te ayuda a elegir Módulo A, B o C
   ↓
3. Construyes tu bot iterando con la IA
   ↓
4. Pruebas tu bot con casos reales
   ↓
5. Llenas la carpeta entregable/ (system prompt + reflexión + capturas)
   ↓
6. Subes el entregable al aula virtual del Curso 2.4 antes del plazo
```

## Los 3 módulos en una línea cada uno

- **Módulo A** — "Quiero un asistente conversacional con buena personalidad para mi tarea X." → Construyes un **Gem** en gemini.google.com (más simple, sin OAuth).
- **Módulo B** — "Quiero que mi asistente actúe sobre Google Workspace por mí (Calendar, Drive, Gmail, Docs, Sheets)." → Necesitas configurar OAuth (te guiamos en `configuracion/02-google-workspace-oauth.md`).
- **Módulo C** — "Quiero encapsular una rutina compleja en una skill reusable, O quiero un asistente que responda usando mis propios PDFs/documentos." → Skills o RAG.

Si dudas cuál te conviene, en `docs/cuando-usar-que.md` está la regla de oro. Y de todas formas tu asistente IA te ayudará a elegir cuando completes el perfil.

## Lo que NO necesitas

- **NO necesitas saber programar.** Si la IA te pide hacer algo técnico, ella misma te dice paso a paso qué tocar y dónde. Si te confundes, le dices "no entiendo" y baja el nivel.
- **NO necesitas pagar nada.** La API de Gemini tiene un plan gratuito que te alcanza de sobra. Codex y Antigravity tienen plan gratuito. Si te piden tarjeta de crédito en algún momento → **detente** y avísale a tu instructora.
- **NO necesitas instalar nada raro.** Solo el editor (Codex, Antigravity o Claude Code) y un navegador con sesión iniciada en tu cuenta `@umce.cl` o Google personal.

## Lo que SÍ necesitas tener listo

- Computador con conexión a internet.
- Cuenta Google activa (puede ser tu `@umce.cl` o personal — depende del módulo, te lo aclaramos cuando llegue el momento).
- Una idea aproximada de **qué tarea repetitiva** quieres automatizar. Si no se te ocurre nada, en `mi-perfil.md` hay sugerencias.
- 4 a 6 horas de tu tiempo, repartidas a lo largo de las 2 semanas que dura el módulo asincrónico.

## Si te trabas

**Primera línea**: dile a tu asistente IA exactamente qué pasa. Es paciente, no se molesta, y va a desbloquearte. Pruebas frases como:
- "No entiendo qué es un system prompt."
- "Me perdí en el paso de OAuth. ¿Puedes repetirme desde el inicio?"
- "Mi bot está inventando datos que no existen. ¿Cómo lo arreglo?"

**Segunda línea**: revisa `docs/cuando-usar-que.md` y `docs/glosario-9-ladrillos.md`. Casi siempre la duda está ahí.

**Tercera línea**: si nada funciona, escríbele a tu instructora del curso o al equipo UDFV (`udfv@umce.cl`). Pega el mensaje exacto que la IA te dio, y dile en qué paso del flujo estabas.

## Una nota sobre confidencialidad

Algunas tareas docentes incluyen información sensible (nombres y notas de estudiantes, RUTs, evaluaciones). **Nunca subas datos personales reales al kit ni los pongas en ejemplos**. Para probar tu bot, inventa nombres y datos (Juana Pérez, RUT 11.111.111-1, etc.). Cuando ya esté funcionando, lo usas con datos reales pero **fuera del kit**, en tu entorno habitual.

## Cuando termines

Cuando tu bot esté listo y la carpeta `entregable/` completa:

1. Comprime la carpeta `entregable/` en un ZIP.
2. Súbelo al aula virtual del Curso 2.4 (link en tu correo institucional).
3. Marca tu participación como completada.

Eso es todo. ¡Buen viaje!

— Equipo UDFV-UMCE.
