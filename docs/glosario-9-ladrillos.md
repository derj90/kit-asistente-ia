# Glosario — Los 9 ladrillos de un asistente con IA

> Los nueve conceptos básicos que estructuran cualquier asistente con IA construido con este kit. Cada uno con su definición, su analogía y un ejemplo concreto. Léelos una vez y vuelve cuando necesites.

---

## 1. API

**Definición técnica**: una API (Application Programming Interface) es una forma estandarizada en que un programa le pide cosas a otro.

**Analogía**: el **menú** de un restaurante. Tú no entras a la cocina; tomas la carta, pides lo que está disponible en la carta, y el cocinero (el otro programa) te lo prepara y te lo trae. La carta es la API: define qué puedes pedir y cómo se pide.

**Ejemplo UMCE**: cuando Moodle te muestra tus cursos del semestre, no genera los datos en el momento — los pide a la API de UCampus mediante una llamada del tipo "dame los cursos del usuario X del año Y". UCampus responde con un listado, y Moodle lo muestra.

---

## 2. LLM (Large Language Model)

**Definición técnica**: un modelo de lenguaje grande es una IA entrenada con millones de textos para predecir, palabra por palabra, qué seguiría diciendo un texto humano en un contexto dado.

**Analogía**: un **cerebro de papel** muy bien leído. Ha leído tanto que es capaz de continuar casi cualquier conversación de manera coherente, en cualquier idioma, sobre casi cualquier tema. Pero no "entiende" en el sentido humano; predice. Eso es importante: por eso a veces inventa con seguridad cosas que no son ciertas.

**Ejemplo UMCE**: Gemini 2.5 Flash es el LLM más conocido de Google. Otros: GPT-5 (OpenAI), Claude Opus (Anthropic), Llama (Meta). Todos hacen lo mismo: predicen texto.

---

## 3. System prompt

**Definición técnica**: el system prompt son las instrucciones permanentes que le das a un LLM antes de empezar a conversar, que definen su rol, estilo, criterios y restricciones.

**Analogía**: la **descripción de cargo** que le das a una persona que acabas de contratar. "Eres asistente de redacción. Eres formal pero cercana. Nunca inventas oficios." Esa descripción no se borra entre conversaciones; permanece.

**Ejemplo UMCE**: el system prompt del "Asistente Redacción UMCE" (`agentes/ejemplo-asistente-redaccion.md`) tiene los cuatro componentes: rol, estilo, criterios, restricciones. Sin él, el bot improvisaría cada vez.

---

## 4. Temperatura

**Definición técnica**: un hiperparámetro de los LLM que va de 0,0 a 1,0 (a veces hasta 2,0) y controla cuán predecible o creativa es la respuesta. 0,0 = la palabra más probable siempre. 1,0 = más variedad y a veces sorpresas.

**Analogía**: el **dial de creatividad**. A 0,0, el bot es predecible: dile lo mismo dos veces y te responde casi igual. A 0,8, dile lo mismo dos veces y te responde dos cosas distintas, con más metáforas, con más riesgo.

**Ejemplo UMCE**: para un bot de redacción institucional, usa temperatura 0,2-0,3 (quieres seriedad). Para un bot de ideación creativa, usa 0,7-0,8 (quieres ideas distintas cada vez).

---

## 5. Agente

**Definición técnica**: un agente es un LLM que, ante una tarea, **decide qué herramientas usar** para cumplirla, en qué orden, y combina los resultados.

**Analogía**: una **conserje hotelero** competente. Tú le dices "necesito flores para una mesa romántica esta noche y un masaje para mañana"; ella sola decide a qué florería llamar, qué spa contactar, en qué orden, cómo coordinar tu reserva, y te devuelve todo resuelto.

**Ejemplo UMCE**: un agente que, cuando le dices "agenda un Consejo de Departamento para la próxima semana con el equipo de Música", consulta tu Calendar, revisa la disponibilidad de los integrantes, crea el evento, envía invitaciones y reserva una sala. Decide qué herramienta (Calendar, Contactos, sistema de reservas) usar en cada paso.

---

## 6. Orquestador

**Definición técnica**: un agente especializado en **repartir trabajo entre varios sub-agentes** según la naturaleza de cada tarea, y luego consolidar resultados.

**Analogía**: una **directora de orquesta**. Ella no toca ningún instrumento; señala al violinista cuándo entrar, al timbal cuándo subir, al chelo cuándo bajar. El resultado es música coherente porque ella coordinó las voces.

**Ejemplo UMCE**: un orquestador que, ante "prepárame un resumen semanal de mi unidad", llama a un sub-agente especializado en leer correos, otro especializado en leer Calendar, otro en revisar tareas pendientes, y combina las tres salidas en un informe único.

---

## 7. Skill

**Definición técnica**: una habilidad encapsulada y reusable que un agente puede invocar para resolver una rutina específica con pasos definidos.

**Analogía**: una **receta de cocina** que vive en tu libro. Cuando quieres hacer pesto, no improvisas — sigues la receta paso a paso. La receta es la skill; la cocinera (el agente) la ejecuta cuando le pides pesto.

**Ejemplo UMCE**: la skill `evaluar-respuesta-abierta` (`skills/ejemplo-evaluar-respuesta-abierta.md`) tiene pasos definidos para tomar una rúbrica + respuesta y producir retroalimentación formativa. El agente la invoca cuando se le pide evaluar — no improvisa cada vez.

---

## 8. MCP (Model Context Protocol)

**Definición técnica**: un estándar abierto, lanzado por Anthropic en 2024 y adoptado por OpenAI y Google en 2025, que define cómo un LLM se conecta a servicios externos (Drive, Calendar, Notion, bases de datos, etc.) para acceder a información o ejecutar acciones.

**Analogía**: el **USB-C del software**. Antes había mil conectores distintos para cada cosa; con USB-C, casi cualquier dispositivo conecta con casi cualquier otro usando el mismo enchufe. MCP es eso para los agentes IA: el mismo "enchufe" sirve para Drive, Calendar, Notion, Gmail y todo lo demás.

**Ejemplo UMCE**: un agente con MCPs configurados de Drive y Calendar puede leer un PDF de tu Drive y, basándose en él, crear automáticamente eventos en tu Calendar. Antes de MCP, cada integración requería código distinto; ahora es un estándar único.

---

## 9. RAG (Retrieval-Augmented Generation)

**Definición técnica**: una técnica donde el LLM **consulta documentos propios** (no su entrenamiento) antes de responder, de modo que sus respuestas estén basadas en tus fuentes específicas y citadas con la fuente exacta.

**Analogía**: un **abogado consultando el código civil antes de opinar**. No improvisa con lo que recuerda; abre el tomo, busca el artículo, lo cita y luego argumenta. Eso garantiza que la respuesta esté basada en una fuente que tú puedes verificar.

**Ejemplo UMCE**: un bot de FAQ para estudiantes que, antes de responder, consulta el reglamento de pregrado vigente y los oficios institucionales del último año. Si le preguntan sobre un trámite, responde citando el oficio específico — no inventa.

---

## La diferencia entre las 3 que más se confunden — Skill / MCP / RAG

| Nombre | Qué hace | Pregunta que responde |
|---|---|---|
| **Skill** | Una rutina propia, encapsulada | "¿Cómo resuelvo este tipo de tarea siguiendo estos pasos?" |
| **MCP** | Una conexión a un servicio externo | "¿Cómo le hablo a este servicio (Drive, Calendar, etc.)?" |
| **RAG** | Consultar documentos propios para responder | "¿Qué dicen mis fuentes sobre esto?" |

Un mismo bot puede usar las tres cosas a la vez. Y se puede confundir cuál es cuál si solo te quedas con la palabra. La diferencia está en la **función**: una skill es una habilidad, un MCP es un enchufe a otro sistema, un RAG es una consulta documentada.
