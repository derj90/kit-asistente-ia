# Carpeta `agentes/`

Aquí van los **system prompts** de los bots que construyas. Un system prompt es el conjunto de instrucciones permanentes que define la personalidad y comportamiento de tu asistente.

## Qué contiene esta carpeta

- `plantilla-agente.md` — Estructura base con los 4 componentes (rol, estilo, criterios, restricciones) que tu asistente IA usará para ayudarte a redactar.
- `ejemplo-asistente-redaccion.md` — Ejemplo completo de un bot para redacción institucional UMCE (Módulo A).
- `ejemplo-orientador-estudiantes.md` — Ejemplo completo de un bot orientador para estudiantes ingresantes (Módulo A).
- `tu-bot.md` — Lo creas tú (o tu asistente IA por ti) cuando empieces a trabajar.

## Cómo se usan

1. Tu asistente IA leerá `plantilla-agente.md` para entender la estructura.
2. Revisará los ejemplos para inspirarse.
3. Creará un archivo nuevo con tu bot (ej. `agentes/asistente-coordinacion.md`).
4. Iterará contigo hasta que el system prompt esté maduro (mínimo 300 palabras, con los 4 componentes claros).
5. Te guiará para pegarlo en el campo "Instructions" de un Gem en gemini.google.com (Módulo A) o en la configuración del agente en Antigravity/Codex (Módulos B y C).

## Por qué importan los 4 componentes

Un system prompt débil produce bots débiles. Si solo le dices a la IA "ayúdame con correos", va a hacer lo que se le ocurra. Si le dices:

1. **Rol** — Quién eres y a quién sirves.
2. **Estilo** — Cómo hablas (formalidad, longitud, tono).
3. **Criterios** — Qué cuenta como "buena respuesta" en tu dominio.
4. **Restricciones** — Qué no debes hacer nunca, qué confidencialidades respetar.

...el bot tiene tracción real. Esa es la diferencia entre un asistente útil y uno que te hace perder tiempo.
