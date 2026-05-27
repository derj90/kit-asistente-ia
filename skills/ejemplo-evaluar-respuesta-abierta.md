# Skill — `evaluar-respuesta-abierta`

> Skill tipo **Nivel 3** (bot con skill propia). Toma una pregunta abierta de evaluación, una rúbrica con criterios, y la respuesta de un estudiante; produce una retroalimentación formativa con puntaje sugerido, fortalezas, debilidades y propuesta concreta de mejora.

## Versión

v0.1 · 2026-05-27

## 1. ¿QUÉ HACE?

Para una evaluación de respuesta abierta (ensayo breve, reflexión, análisis de caso), produce:

1. Un puntaje sugerido según la rúbrica entregada.
2. Una retroalimentación formativa estructurada (fortalezas + debilidades + sugerencia concreta).
3. Una pregunta orientadora para que el estudiante avance.

La retroalimentación está pensada para que la docente **revise, ajuste y entregue al estudiante** — no se entrega directamente al estudiante sin revisión humana.

## 2. ¿CUÁNDO SE INVOCA?

- Cuando la docente pega una rúbrica + una respuesta de estudiante y pide "evalúa esto" o "dame retroalimentación".
- Cuando se procesa por lotes un set de respuestas con la misma rúbrica.

## 3. ENTRADA

**Obligatorios**:
- `pregunta`: el enunciado de la evaluación tal como se entregó al estudiante.
- `rubrica`: criterios de evaluación con niveles de logro (idealmente con descriptores, no solo puntajes).
- `respuesta_estudiante`: el texto que respondió el estudiante. Debe estar anonimizado (sin nombre real, RUT ni datos personales identificables).

**Opcionales**:
- `respuesta_modelo`: una respuesta de referencia ideal (mejora la consistencia del bot).
- `nivel_curso`: pregrado · postgrado · cierto curso específico (mejora calibración).

**Si la respuesta del estudiante NO está anonimizada**, el bot:
1. Lo advierte explícitamente.
2. Pregunta si la docente quiere que el bot la anonimice antes de procesar.
3. No procede hasta confirmación.

## 4. PASOS INTERNOS

1. **Validar anonimato** — Detectar si hay nombres propios, RUTs, correos `@umce.cl` o equivalentes en la respuesta. Si los hay, alertar.
2. **Leer la rúbrica completa** — Identificar cada criterio y sus niveles. Si la rúbrica no tiene descriptores (solo "1 a 7"), advertir que la evaluación va a ser menos precisa.
3. **Leer la respuesta** — Marcar internamente: tesis o postura central, evidencias usadas, articulación lógica, errores conceptuales, errores formales (ortografía, sintaxis).
4. **Aplicar la rúbrica criterio por criterio** — Para cada criterio: identificar el nivel de logro alcanzado y justificarlo con una cita textual de la respuesta.
5. **Sintetizar fortalezas** — Identificar las 2-3 cosas más sólidas de la respuesta.
6. **Sintetizar debilidades** — Identificar las 1-2 brechas principales (no más, para no abrumar).
7. **Formular una sugerencia concreta** — Una acción específica que el estudiante podría hacer para mejorar.
8. **Formular una pregunta orientadora** — Una pregunta abierta que invite al estudiante a pensar más profundo (sin dar la respuesta).
9. **Calcular puntaje** — Promediar o sumar según la rúbrica. Indicar siempre que es **sugerido** y que requiere revisión humana.

## 5. SALIDA — Formato exacto

```
EVALUACIÓN SUGERIDA — [TÍTULO DE LA EVALUACIÓN]
(Esta evaluación fue generada por IA y requiere revisión y ajuste humano antes de entregarse.)

EVALUACIÓN POR CRITERIO

Criterio 1: [Nombre del criterio]
  Nivel observado: [N/máx]  ·  Justificación: "[cita textual breve]" — [explicación de 1-2 frases].

Criterio 2: [...]
  Nivel observado: [N/máx]  ·  Justificación: "[cita textual breve]" — [explicación].

[...]

PUNTAJE SUGERIDO: [N] / [máx]  (Nota aproximada: [X,X])

FORTALEZAS
1. [Fortaleza 1, con referencia a la respuesta.]
2. [Fortaleza 2, con referencia a la respuesta.]
3. [Fortaleza 3 — opcional.]

BRECHAS PRINCIPALES
1. [Brecha 1, descrita con calma y sin juicio.]
2. [Brecha 2 — opcional.]

SUGERENCIA CONCRETA
[Una acción específica que el estudiante podría hacer. Ej: "Vuelve a leer la sección X del texto base; allí hay un concepto que ayudaría a sostener tu argumento sobre Y."]

PREGUNTA ORIENTADORA
[Pregunta abierta que el estudiante puede llevarse para pensar.]

— Fin de la evaluación sugerida —
```

## 6. CRITERIOS DE CALIDAD

1. Cada nivel de logro asignado está respaldado por una cita textual de la respuesta. Sin cita = no se asigna.
2. La retroalimentación NUNCA emite juicio personal sobre el estudiante ("se nota que no estudiaste"). Sí señala lo que se observa en el texto.
3. Las fortalezas se dicen primero. Las brechas vienen después y son específicas, no genéricas.
4. La sugerencia concreta es accionable: el estudiante debería poder hacer algo específico el día siguiente.
5. El puntaje siempre va etiquetado como "sugerido" + advertencia de revisión humana.
6. Si la respuesta del estudiante es muy breve o ininteligible, el bot NO inventa contenido; explica que no hay material suficiente para evaluar y sugiere conversar directamente con el estudiante.

## 7. RESTRICCIONES

- **Nunca procesar una respuesta sin anonimizar** (sin advertencia y confirmación explícita).
- Nunca atribuir intención al estudiante ("no quiso esforzarse", "no entendió"); solo describir lo observado.
- Nunca emitir juicios sobre capacidades cognitivas, salud mental ni circunstancias personales del estudiante.
- Nunca usar comparaciones con otros estudiantes ("a diferencia de tus compañeros").
- Nunca presentar el resultado como definitivo. Siempre incluir la advertencia: "Esta evaluación fue generada por IA y requiere revisión y ajuste humano antes de entregarse."
- Si la rúbrica tiene criterios ambiguos o contradictorios, señalarlo a la docente antes de evaluar.
- Si la respuesta toca temas sensibles del estudiante (situación familiar, salud mental, vulneración), señalarlo y sugerir que la docente conversetenga con la persona antes de evaluar fríamente.

## 8. PRUEBA DE LA SKILL

**Entrada**:

```
pregunta: "Reflexiona sobre el rol del docente como mediador del aprendizaje en el contexto
de educación a distancia. Apoya tu reflexión en al menos un autor visto en clase."

rubrica:
- Criterio 1 — Apropiación conceptual (0-3 puntos): el texto demuestra comprensión de los conceptos
  clave de mediación pedagógica.
- Criterio 2 — Uso de fuentes (0-2 puntos): cita y articula al menos un autor de manera pertinente.
- Criterio 3 — Reflexión personal (0-2 puntos): hay una postura argumentada del estudiante.
- Criterio 4 — Forma y coherencia (0-1 punto): ortografía, sintaxis, coherencia textual.

respuesta_estudiante: "[Texto de aprox. 250 palabras del estudiante, anonimizado.]"
```

**Salida esperada (resumen)**:

Una evaluación sugerida con puntajes por criterio justificados con citas, fortalezas (2-3), una o dos brechas, sugerencia concreta de mejora, pregunta orientadora, y advertencia clara de revisión humana.

## 9. ITERACIONES

- **v0.1** (2026-05-27): Borrador inicial.
- **v0.2**: pendiente — ajustar luego de probar con respuestas reales anonimizadas.
