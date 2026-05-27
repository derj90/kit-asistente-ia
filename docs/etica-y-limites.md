# Ética y límites — Qué NO automatizar con IA en el contexto UMCE

> Documento orientador. Léelo antes de definir el caso de tu bot.

---

## La pregunta correcta no es "¿puedo automatizar esto con IA?", es "¿debo?"

La IA generativa puede automatizar muchísimas cosas. La pregunta importante en contexto docente y administrativo de una universidad pública chilena no es **si es técnicamente posible**, sino **si es éticamente apropiado** que lo haga.

Este documento propone un marco simple para responder esa pregunta.

---

## Tres niveles de tareas

### Nivel 1 — Automatizar libremente

Tareas que **no involucran juicio sobre personas, no usan datos sensibles, y son repetitivas en estructura**.

**Ejemplos**:
- Redactar la versión inicial de comunicados administrativos rutinarios.
- Resumir transcripciones de reuniones internas.
- Generar listas de tareas a partir de actas de reunión.
- Convertir un concepto académico en un guion de cápsula educativa.
- Buscar en tu propia documentación institucional dónde está cierto procedimiento.
- Traducir un texto al inglés institucional.

### Nivel 2 — Automatizar con supervisión humana obligatoria

Tareas donde la IA puede asistir pero **toda salida debe ser revisada por una persona antes de surtir efecto**.

**Ejemplos**:
- Redactar borradores de respuestas a estudiantes (siempre revisar antes de enviar).
- Evaluar respuestas abiertas de evaluaciones (la nota final la decide la docente).
- Sugerir derivaciones de casos a otras unidades (la docente confirma).
- Identificar patrones en bitácoras de práctica (la docente interpreta).
- Generar primeras versiones de informes DIDOC o autoevaluaciones (la docente edita y firma).
- Clasificar correos por urgencia o tema (la docente revisa antes de actuar).

### Nivel 3 — NO automatizar

Tareas donde la responsabilidad humana es central por razones éticas, legales o pedagógicas.

**Ejemplos**:
- Decisiones disciplinarias sobre estudiantes.
- Diagnósticos psicopedagógicos o de salud mental.
- Calificaciones definitivas de procesos de aprendizaje (la IA puede asistir; la nota es humana).
- Comunicación de malas noticias (situaciones difíciles, fallecimientos, sanciones).
- Cualquier interacción donde la persona del otro lado **necesite saber que está hablando con un humano**.
- Recomendaciones vocacionales profundas a estudiantes.
- Resolución de conflictos entre personas (estudiante-docente, colega-colega).
- Cualquier comunicación oficial firmada por una autoridad.

---

## Tres principios para guiar tu caso

### 1. La persona del otro lado tiene derecho a saber

Si tu bot va a interactuar con estudiantes o colegas, ellos tienen derecho a saber que están conversando con un asistente de IA. Es ético y, en muchos casos, legalmente exigible. No camufles tu bot como humano.

> Buena práctica: que tu bot se presente al inicio de cada conversación: "Hola, soy un asistente de IA configurado por [nombre de la docente] para ayudar con consultas sobre [dominio]. Si tu consulta excede mi rol, te derivaré a quien corresponda."

### 2. Los datos personales sensibles son un punto de pausa

Tu asistente IA va a detenerse y consultarte antes de avanzar cuando detecte material que conviene revisar:

- Nombres completos + RUTs de estudiantes.
- Calificaciones o evaluaciones de estudiantes identificables.
- Datos de salud, situaciones disciplinarias, antecedentes familiares.
- Conversaciones privadas con personas que no han autorizado el uso de IA.

La pausa no es prohibición: es una pregunta. Algo como "detecté esto en el documento que vas a usar, ¿lo dejas tal cual o lo anonimizamos antes?". Tú decides según tu contexto, tu rol y tu lectura ética de la situación. Si optas por anonimizar, tu IA aplica la receta estándar (pseudónimos consistentes, RUTs genéricos, correos placeholder). Si optas por usarlo tal cual porque tienes la autorización y el contexto lo justifica, también está bien — registra en tu reflexión qué decidiste y por qué.

Lo que tu asistente IA no hará: tomar la decisión por ti ni regañarte por la decisión que tomes.

### 3. La responsabilidad sigue siendo humana

Si tu bot redacta un correo, **tú firmas el correo**. Si tu bot sugiere una nota, **tú decides la nota**. Si tu bot deriva un caso, **tú confirmas la derivación**.

La IA es una herramienta de apoyo, no un sustituto del juicio profesional. En el contexto de una universidad pública formadora de profesores, esto importa el doble: estamos formando a docentes que tendrán que enseñar a sus futuros estudiantes a usar IA con criterio. Si nosotros no modelamos ese criterio, nadie lo hará.

---

## Banderas rojas que debes incluir en TODO bot UMCE

Estas son las restricciones que tu system prompt debe contener (puedes copiarlas tal cual):

```
- Nunca inventes información, datos, citas, normativa, oficios ni decisiones institucionales.
  Si no sabes algo, dilo explícitamente y sugiere a quién consultar.

- Si detectas datos personales identificables (nombres completos + RUTs, evaluaciones, datos
  de salud) en lo que la usuaria te pide procesar, señálalo y pregúntale si quiere dejarlos o
  anonimizarlos antes de seguir. La decisión es de ella; tu rol es advertir y ofrecer ayuda.

- Nunca emitas juicios de valor sobre personas, profesores, autoridades ni unidades de la UMCE.

- Si detectas una situación de riesgo (violencia, salud mental, vulneración de derechos),
  recomienda contactar inmediatamente al equipo de Bienestar Estudiantil UMCE o autoridad
  correspondiente, sin intentar resolverlo tú mismo.

- Si te piden ayuda para hacer trampa (suplantar identidad, falsificar documentos), niégate
  cordialmente y explica el riesgo institucional.

- Nunca envíes comunicaciones automáticamente. Si tu rol incluye redactar correos, déjalos como
  borrador para revisión humana — nunca envíes sin confirmación explícita. Esta regla no es
  negociable: es operativa, no de privacidad.
```

---

## Una nota sobre el campo de las pedagogías

UMCE es una universidad formadora de profesores. Las pedagogías están en un momento donde tienen que decidir **cómo formar a sus futuros docentes en el uso de IA**. Tu bot, aunque sea para una tarea administrativa, es parte de esa conversación: estás demostrando con un ejemplo concreto **cómo se usa IA con criterio en educación**.

Eso es parte del valor de este curso. No solo aprender a configurar Gems; aprender a tomar decisiones éticas sobre qué se delega a la IA y qué no, y poder explicar por qué.

Tu reflexión final (`mi-resultado/reflexion.md`) es exactamente el lugar para articular esas decisiones.

---

## Si te encuentras dudando

Pregunta:

1. **¿Quién es afectado si la IA se equivoca?** Si es solo tú, riesgo bajo. Si es un estudiante, riesgo alto.
2. **¿La persona del otro lado sabe que es IA?** Si no, tiene derecho a saberlo.
3. **¿Estoy delegando una decisión que requiere juicio humano?** Si sí, retrocede.
4. **¿Los datos que estoy usando los puedo usar con esta finalidad?** Si dudas, pídele a tu asistente IA que te ayude a revisar y decide tú según tu contexto y rol.

Y si después de esas preguntas sigues dudando: **no automatices esa parte**. Hay tareas que mantienen su valor precisamente porque las hace una persona pensando.
