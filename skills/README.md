# Carpeta `skills/`

Aquí van las **skills** que definas para tu bot. Una skill es una **habilidad encapsulada y reusable**: una rutina concreta con entrada, pasos internos y salida claras, que el bot invoca cuando lo necesita.

## Cuándo usar skills

Si detectas que en tu trabajo haces una rutina de **5 o más pasos similares** cada vez (ej. "para resumir una bitácora de práctica, primero extraigo X, después agrupo Y, después contrasto Z, después escribo W"), conviene encapsular esa rutina como skill.

Beneficios:
- El bot no improvisa cada vez.
- Tú no tienes que repetir las instrucciones a la IA cada vez.
- La rutina queda documentada y otras personas pueden reutilizarla.

## Skill vs prompt simple

- **Prompt simple**: "Resume esta bitácora." → la IA improvisa cada vez.
- **Skill**: "Resume esta bitácora **siguiendo el procedimiento `resumir-bitacora-practica`**." → el bot ejecuta los pasos definidos, en el orden definido, con el formato definido.

## Cómo se usan

1. Tu asistente IA lee `plantilla-skill.md` para entender la estructura.
2. Revisa los ejemplos (`ejemplo-generar-capsula-educativa.md`, `ejemplo-evaluar-respuesta-abierta.md`).
3. Crea un archivo nuevo con tu skill (ej. `skills/resumir-bitacora-practica.md`).
4. Te ayuda a probarla en Antigravity o Codex, donde el agente puede invocar la skill al detectar la palabra clave o intent correspondiente.

## Skill vs MCP vs RAG (lo tres se confunden)

- **Skill** — Una habilidad propia del bot (sus pasos internos para resolver una tarea). No requiere conectarse a sistemas externos.
- **MCP (Model Context Protocol)** — El "USB-C" que conecta al bot con servicios externos (Google Workspace, Notion, n8n, etc.). Permite que el bot **actúe** sobre esos servicios.
- **RAG (Retrieval-Augmented Generation)** — El bot **responde** consultando documentos propios antes de redactar.

Mismo bot puede usar las tres cosas, pero son cosas distintas.

> Detalle profundo de esta distinción en `docs/glosario-9-ladrillos.md` y `docs/cuando-usar-que.md`.
