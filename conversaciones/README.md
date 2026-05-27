# Carpeta `conversaciones/`

Aquí guardas las **pruebas que le hagas a tu bot**: capturas de pantalla, transcripciones, registros de cómo respondió frente a casos típicos y casos límite.

Esta carpeta es parte importante de tu entregable: la rúbrica del curso evalúa explícitamente la **calidad de las conversaciones de prueba** (criterio 3, 25% del puntaje).

## Qué tipo de archivos van aquí

- **Transcripciones**: copia-pega del intercambio con tu bot a un archivo `.md`. Es lo más ligero y fácil de mostrar.
- **Capturas de pantalla**: imágenes `.png` o `.jpg` del bot en acción. Útil para mostrar el contexto visual (ej. el Gem funcionando en gemini.google.com).
- **Notas tuyas**: tu lectura de cada prueba — qué salió bien, qué no, qué ajustaste después.

## Qué pruebas debes hacer (mínimo)

La rúbrica pide **al menos 2 conversaciones de prueba**, una de cada tipo:

### 1. Caso típico — el bot resuelve bien lo que se espera

Una conversación que demuestre que **tu bot cumple su rol cuando se le pide algo dentro de su dominio**. Debe verse natural, en tono apropiado, con la calidad que definiste en los criterios de tu system prompt.

> Ejemplo: si tu bot es "Asistente de redacción institucional", una prueba típica es pedirle que redacte un comunicado real (anonimizado), y mostrar que el resultado tiene la estructura, tono y nivel que esperabas.

### 2. Caso límite / fuera de rol — el bot maneja bien la frontera

Una conversación que demuestre que **tu bot reconoce cuándo algo está fuera de su rol** y redirige cordialmente, sin inventar respuestas ni salirse de las restricciones que le pusiste.

> Ejemplo: si tu bot es "Asistente de redacción institucional", una prueba de borde es pedirle que escriba un poema, un texto comercial, o un texto con tono confrontacional. Lo que esperas es que diga: "Esto excede mi rol; te conviene un asistente generalista" o "Te propongo una versión institucional asertiva sin descalificar".

### 3. (Opcional pero recomendado) Caso difícil — el bot responde bien a algo complejo

Si tu bot tiene un dominio en el que hay situaciones delicadas (datos sensibles, decisiones controversiales, emociones), una prueba que demuestre cómo responde frente a eso suma muchísimo.

## Cómo guardar una transcripción

Crea un archivo `.md` en esta carpeta. Formato sugerido:

```
# Prueba — [nombre breve de la prueba]

**Bot**: [nombre del Gem o agente]
**Modelo**: Gemini 2.5 Flash
**Temperatura**: 0,3
**Fecha**: [día-mes-año]
**Tipo de caso**: [típico / fuera de rol / difícil]

## Lo que le pedí

[Copia textual de tu mensaje al bot.]

## Lo que respondió

[Copia textual de la respuesta del bot, completa.]

## Mi lectura

[2-4 frases tuyas — qué te pareció, qué salió bien, qué falta, qué vas a ajustar.]
```

Ya hay un archivo de ejemplo (`ejemplo-prueba-bot-redaccion.md`) para que veas el formato.

## Cómo guardar capturas

1. Toma la captura de pantalla en tu computador (Mac: `Cmd + Shift + 4` · Windows: `Win + Shift + S`).
2. Renómbrala con algo descriptivo: `01-prueba-caso-tipico.png`, `02-prueba-fuera-de-rol.png`.
3. Guárdala en esta carpeta `conversaciones/`.
4. Idealmente, acompáñala con un `.md` que explique qué se ve en la captura.

> Si quieres anonimizar partes de una captura, usa Vista Previa (Mac) o Paint (Windows) para tapar nombres, correos, RUTs. Nunca subas capturas con datos personales sensibles.

## Para el entregable final

Cuando estés cerrando tu producto:

1. Selecciona tus 2 (o 3) mejores conversaciones de prueba.
2. Cópialas a `entregable/capturas/` (las imágenes) y referéncialas en tu reflexión.
3. En la reflexión, comenta qué aprendiste de cada prueba.
