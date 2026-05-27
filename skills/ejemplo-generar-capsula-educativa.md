# Skill — `generar-capsula-educativa`

> Skill tipo **Módulo C.1**. Toma un concepto, un público objetivo y un tiempo, y produce el guion de una cápsula educativa breve estructurada según buenas prácticas de microlearning UDFV.

## Versión

v0.1 · 2026-05-27

## 1. ¿QUÉ HACE?

Convierte un concepto académico (definición, procedimiento, normativa, herramienta) en un **guion estructurado para una cápsula educativa de 90 a 180 segundos**, listo para grabar en video o audio, con apertura, desarrollo, ejemplo aplicado y cierre. La salida sigue una estructura pedagógica reproducible que facilita la producción.

## 2. ¿CUÁNDO SE INVOCA?

Cuando el usuario:
- Pida explícitamente "una cápsula educativa sobre X" / "un microguion sobre X" / "explica X en 2 minutos".
- Pegue un concepto académico y diga "conviértelo en cápsula".
- Esté preparando material para un curso autoformativo o un boletín UDFV.

## 3. ENTRADA

**Obligatorios**:
- `concepto`: qué se enseña (ej. "qué es una skill en IA", "cómo se solicita una postergación de evaluación", "principios del Diseño Universal de Aprendizaje").
- `publico_objetivo`: a quién va dirigido (ej. "docentes UMCE sin formación en TI", "estudiantes de primer año de pedagogía", "personal administrativo").
- `duracion_segundos`: duración objetivo en segundos (90, 120, 150 o 180).

**Opcionales (mejoran la salida)**:
- `ejemplo_real`: un caso concreto que el bot puede usar para ilustrar.
- `tono`: cercano · neutro · institucional (default: cercano).
- `formato_salida`: solo guion · guion + sugerencias visuales (default: solo guion).

**Si falta un dato obligatorio**, el bot pregunta antes de generar nada.

## 4. PASOS INTERNOS

1. **Validar entrada** — Confirmar que están los 3 datos obligatorios. Si no, preguntar por los faltantes (una sola pregunta consolidada).
2. **Reformular el concepto** — Escribir internamente una definición de una frase del concepto, adaptada al público objetivo.
3. **Identificar el "para qué"** — En una frase, articular por qué este concepto le importa al público objetivo (motivación pedagógica).
4. **Construir el ejemplo aplicado** — Si el usuario entregó `ejemplo_real`, usarlo. Si no, generar un ejemplo plausible del contexto UMCE (anonimizado).
5. **Diseñar la cápsula con estructura GOLE** — Estructura de 4 momentos:
   - **G — Gancho** (10-15% del tiempo): pregunta o situación que abre.
   - **O — Orientación** (25-30%): qué es y para qué sirve.
   - **L — Lo concreto** (35-40%): ejemplo aplicado paso a paso.
   - **E — Encuadre** (15-20%): qué hacer ahora con esto, llamada a la acción.
6. **Calcular palabras** — Aproximar a 130 palabras por minuto (ritmo natural locutor). Para 120 s → ~260 palabras.
7. **Redactar el guion** — En el tono indicado, con secciones claramente etiquetadas.
8. **(Si aplica) Sugerencias visuales** — Si `formato_salida` incluye visuales, agregar al final de cada bloque entre corchetes una sugerencia simple: `[Visual: persona caminando por pasillo UMCE]`.

## 5. SALIDA — Formato exacto

```
CÁPSULA EDUCATIVA — [CONCEPTO]
Público: [público objetivo]  ·  Duración: [N] s  ·  Palabras aprox.: [N]

GANCHO ([X] s aprox.)
[Texto del gancho, 1-2 frases. Pregunta o situación.]

ORIENTACIÓN ([X] s aprox.)
[Qué es el concepto, en lenguaje del público. 2-3 frases.]
[Para qué sirve. 1 frase con verbo de acción.]

LO CONCRETO ([X] s aprox.)
[Ejemplo aplicado paso a paso. 3-5 frases concretas.]

ENCUADRE ([X] s aprox.)
[Qué hace el espectador con esto en su semana. 1-2 frases.]
[Llamada a la acción concreta. 1 frase.]

— Fin del guion —

NOTAS DE PRODUCCIÓN
- Ritmo sugerido: [pausado / normal / dinámico]
- Tono recomendado del locutor: [cercano / informativo / inspirador]
- Posible imagen de portada (si es video): [sugerencia breve]
```

## 6. CRITERIOS DE CALIDAD

1. La duración real del guion (al medir palabras / 130) está a ±10% de la solicitada.
2. El gancho NO empieza con "En este video vamos a hablar de" ni equivalentes — siempre con pregunta, dato sorprendente o situación.
3. El ejemplo de "Lo concreto" es **verificable y realista** en el contexto UMCE.
4. El encuadre da una acción concreta (no abstracta tipo "reflexiona sobre esto").
5. El lenguaje está adaptado al público: si es para "docentes UMCE sin formación en TI", no aparecen términos como "endpoint", "OAuth", "stack" sin explicación.

## 7. RESTRICCIONES

- Nunca inventar normativa, oficios ni decisiones institucionales para usarlos como ejemplo. Si necesita un ejemplo institucional, generarlo como hipotético claramente etiquetado.
- Nunca nombrar a personas reales de la UMCE en los guiones (autoridades, profesores, estudiantes). Usar roles genéricos: "una jefa de carrera", "un estudiante de tercer año".
- Si el concepto solicitado es controversial (política partidista, religión, juicio sobre autoridades), declinar cordialmente y sugerir reformular hacia el plano técnico-pedagógico.
- Nunca incluir datos sensibles en los ejemplos (RUTs, notas, situaciones disciplinarias reales).

## 8. PRUEBA DE LA SKILL

**Entrada**:

```
concepto: "Qué es un system prompt en IA"
publico_objetivo: "Docentes UMCE sin formación técnica"
duracion_segundos: 120
ejemplo_real: (vacío)
tono: cercano
formato_salida: guion + sugerencias visuales
```

**Salida esperada (aproximada)**:

```
CÁPSULA EDUCATIVA — Qué es un system prompt en IA
Público: Docentes UMCE sin formación técnica  ·  Duración: 120 s  ·  Palabras aprox.: 260

GANCHO (15 s)
¿Alguna vez le pediste algo a un asistente de IA y la respuesta no se pareció en nada a lo que querías?
Probablemente no fue culpa tuya. Fue culpa de lo que la IA no sabía de ti antes de empezar.
[Visual: docente frente a computador con cara de extrañeza]

ORIENTACIÓN (30 s)
Un system prompt son las instrucciones permanentes que le das a un asistente de IA antes de
empezar a conversar. Es como contratar a una persona y entregarle su descripción de cargo:
quién es, cómo habla, qué hace bien, qué no debe hacer. Sirve para que cada respuesta que te
dé esté alineada con tu trabajo, tu contexto y tus estándares.
[Visual: mano escribiendo en un documento titulado "Instrucciones del asistente"]

LO CONCRETO (45 s)
Imagina que necesitas un asistente para responder consultas de estudiantes de tu departamento.
Sin system prompt, le preguntas algo y improvisa. Con system prompt, le dices: "Eres un orientador
para estudiantes de primer año de Pedagogía en Música UMCE. Hablas con calidez, tuteas, y derivas
a la jefatura de carrera cuando no sabes algo." Desde ese momento, cada respuesta va a respetar
ese rol. Si una estudiante pregunta cómo cambiarse de carrera, el bot ya sabe que tiene que
derivarla en vez de improvisar.
[Visual: dos pantallas en paralelo — sin instrucciones vs con instrucciones]

ENCUADRE (30 s)
Esta semana, antes de pedirle algo a tu asistente IA, dedica diez minutos a escribirle quién es y
qué hace. Te va a ahorrar horas. Y en el Curso 2.4 vamos a aprender a hacer system prompts
sólidos, con los cuatro componentes que importan.
[Visual: cierre con logo UDFV]

— Fin del guion —

NOTAS DE PRODUCCIÓN
- Ritmo sugerido: normal con pausas en transiciones
- Tono recomendado del locutor: cercano, ligeramente cómplice
- Posible imagen de portada: docente y robot dándose la mano sobre un escritorio
```

## 9. ITERACIONES

- **v0.1** (2026-05-27): Borrador inicial.
- **v0.2**: pendiente — ajustar palabras-por-minuto según pruebas reales de locución.
