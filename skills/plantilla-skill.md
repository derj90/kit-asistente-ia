# Plantilla — Skill encapsulada

> Copia esta plantilla, renómbrala `[nombre-de-tu-skill].md` (con guiones, en minúsculas) y complétala con tu asistente IA.

---

## Nombre de la skill

`[nombre-skill-en-kebab-case]` — ej. `resumir-bitacora-practica` · `redactar-acta-de-reunion` · `evaluar-respuesta-abierta` · `generar-capsula-educativa`

## Versión

v0.1 — borrador inicial · [Fecha]

---

## 1. ¿QUÉ HACE? (en 1-2 frases)

[Descripción concisa de la tarea que esta skill resuelve. Ej: "Toma una bitácora semanal de práctica profesional escrita por un estudiante y produce un resumen de 200 palabras con avances, dificultades y compromisos para la próxima semana."]

---

## 2. ¿CUÁNDO SE INVOCA?

[Qué palabras o situaciones disparan que el bot llame a esta skill. Ej: "Cuando el usuario diga 'resume esta bitácora', 'sintetiza el avance del estudiante X', o me pegue un texto que claramente sea una bitácora semanal."]

---

## 3. ENTRADA — Qué necesita la skill para funcionar

**Datos obligatorios**:
- [Ej: el texto completo de la bitácora]
- [Ej: el nombre del estudiante (puede ser pseudónimo)]
- [Ej: la semana a la que corresponde]

**Datos opcionales (mejoran la salida si están)**:
- [Ej: la bitácora de la semana anterior, para detectar continuidad]
- [Ej: los compromisos pendientes del estudiante]

**Si falta un dato obligatorio**, el bot debe **pedirlo explícitamente** antes de ejecutar. Nunca debe inventar el dato faltante.

---

## 4. PASOS INTERNOS — Cómo se ejecuta la skill

> Numera los pasos. Cada paso debe ser concreto y verificable. Esto es lo que el bot va a hacer internamente al invocar la skill.

1. **[Paso 1]** — [Descripción concreta. Ej: "Leer la bitácora completa y extraer 3 elementos: (a) acciones realizadas, (b) dificultades encontradas, (c) reflexiones del estudiante."]
2. **[Paso 2]** — [Ej: "Agrupar las acciones por dominio: pedagógico / vincular / administrativo."]
3. **[Paso 3]** — [Ej: "Identificar la dificultad principal (la que aparece con más insistencia o más detalle en el texto)."]
4. **[Paso 4]** — [Ej: "Detectar 1-2 compromisos para la próxima semana basándose en las dificultades."]
5. **[Paso 5]** — [Ej: "Redactar el resumen en el formato definido en sección SALIDA."]

---

## 5. SALIDA — Qué produce la skill

**Formato exacto**:

[Describe el formato literal que el bot debe producir. Si es estructurado, usa una plantilla con placeholders.]

```
RESUMEN DE BITÁCORA — [NOMBRE ESTUDIANTE] — SEMANA [N]

Avances de la semana:
- [Avance 1]
- [Avance 2]
- [Avance 3]

Dificultad principal:
[Una frase que resuma el desafío central de la semana.]

Compromisos para la próxima semana:
1. [Compromiso 1]
2. [Compromiso 2]

Observación pedagógica:
[2-3 frases del bot con su lectura del progreso, en tono profesional pero cálido.]
```

**Longitud objetivo**: [Ej: "Entre 150 y 250 palabras."]

---

## 6. CRITERIOS DE CALIDAD

Una buena ejecución de esta skill cumple:

1. [Ej: "Los avances mencionados están explícitamente en la bitácora — no se inventan."]
2. [Ej: "Los compromisos son específicos y verificables, no genéricos."]
3. [Ej: "La observación pedagógica nunca juzga negativamente al estudiante; señala con calma lo que se observa."]
4. [Ej: "El resumen mantiene la voz del estudiante donde se cita una frase suya literal."]

---

## 7. RESTRICCIONES

- [Ej: "Si la entrada trae datos identificables (nombres reales, RUTs, instituciones de práctica) y no se pidieron explícitamente, avisar al usuario y preguntar si los deja o los reemplaza por placeholders antes de continuar."]
- [Ej: "Nunca emitir juicios sobre la institución donde el estudiante hace la práctica."]
- [Ej: "Si la bitácora menciona situaciones de riesgo (violencia escolar, vulneración de derechos), el bot debe destacarlo en una sección aparte llamada 'Situación que requiere derivación' y sugerir contactar a la coordinación de prácticas."]

---

## 8. PRUEBA DE LA SKILL

> Define al menos un caso de prueba con entrada y salida esperada, para verificar que funciona bien antes de usarla en producción.

**Entrada de prueba**:

```
[Pega aquí un ejemplo de bitácora o de la entrada que sea para tu caso. Si trae datos identificables y prefieres no dejarlos en este archivo, tu asistente IA puede anonimizarlos contigo antes de pegar.]
```

**Salida esperada (aprox.)**:

```
[Pega aquí cómo esperarías que se viera la salida ideal.]
```

---

## 9. NOTAS DE ITERACIÓN

- **v0.1** ([fecha]): Borrador inicial.
- **v0.2** ([fecha]): [Qué ajustaste]
