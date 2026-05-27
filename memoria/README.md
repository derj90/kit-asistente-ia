# Carpeta `memoria/`

Aquí pones los **documentos que tu bot debe conocer**: PDFs, oficios, syllabus, normativas, guías internas, FAQs anteriores. Esta carpeta es lo que en jerga técnica se llama "base de conocimiento" o "fuente para RAG" (Retrieval-Augmented Generation).

## Qué tipo de archivos van aquí

- **PDFs**: oficios, reglamentos, calendarios académicos, syllabus, instructivos.
- **Documentos Word / Markdown**: guías internas, FAQs preexistentes, protocolos.
- **Texto plano**: transcripciones de reuniones, apuntes propios.
- **CSVs o tablas simples**: listados de contactos por unidad, calendarios, etc.

## Qué te va a avisar tu asistente IA

Antes de que un documento entre como fuente de tu bot, tu IA hace un escaneo rápido y te avisa si detecta:

- Nombres completos de estudiantes junto a notas, evaluaciones o situaciones disciplinarias.
- RUTs reales, correos institucionales identificables o datos de salud.
- Material cuya circulación pueda estar restringida por normativa institucional.

Te lo señala con una pregunta tipo "detecté esto, ¿lo dejas o lo anonimizamos antes de usarlo como fuente?". Tú decides. Si quieres usar datos reales, los usas; si prefieres anonimizar, tu IA lo hace contigo en un minuto.

> Si quieres una segunda opinión sobre si conviene usar un documento, pídesela a tu asistente IA o consulta a quien corresponda en tu unidad. La decisión final es tuya.

## Cómo se usan estos documentos

Tu asistente IA puede usarlos de tres maneras según el nivel que estés trabajando:

### Nivel 1 con Gem
Subes 2-3 PDFs pequeños al campo "Knowledge" del Gem en gemini.google.com. El Gem los usará al responder. Funciona bien con pocos documentos estables (calendario académico, reglamento de pregrado, etc.).

### Nivel 4 con Antigravity / Codex
Pones los archivos en esta carpeta `memoria/`. El asistente IA los lee al inicio de la conversación y los usa al responder. Funciona bien con cualquier cantidad y se actualiza cada vez que ejecutas.

### Nivel 4 con NotebookLM
Subes los archivos a un cuaderno de NotebookLM (https://notebooklm.google.com). El bot vive ahí y responde citando las fuentes con números. Funciona muy bien para muchos documentos (hasta cientos de páginas).

> Decisión rápida: pocos docs estables → Gem. Volumen alto y necesidad de citas → NotebookLM. Quieres el bot en tu propio entorno → Antigravity / Codex con esta carpeta. Detalle en `docs/cuando-usar-que.md`.

## Anonimización rápida (si decides usarla)

Si optas por anonimizar un documento antes de cargarlo, tu asistente IA puede hacerlo por ti. Receta estándar que aplica:

1. Reemplaza nombres reales por nombres ficticios consistentes (María Pérez, Juan Soto, etc.).
2. Reemplaza RUTs por RUTs genéricos (11.111.111-1, 22.222.222-2).
3. Reemplaza correos por placeholders (`estudiante1@umce.cl`, `docente.modelo@umce.cl`).
4. Quita datos de salud, situaciones disciplinarias específicas, montos económicos personales.
5. Mantiene la estructura del documento (encabezados, secciones, formatos) intacta.

Pídeselo así: "anonimiza este documento antes de que lo use como fuente". También puedes pedir un escaneo previo ("revisa qué datos identificables tiene") y decidir caso a caso qué dejas y qué cambias.

## Buena práctica

- Pon un archivo por tema, con nombre descriptivo en kebab-case: `reglamento-pregrado-2024.pdf`, `calendario-academico-2026.pdf`, `faq-trampolin-cohorte-2025.md`.
- Si el documento es muy largo (más de 100 páginas), conviene **fragmentarlo** por capítulos o secciones.
- Mantén la carpeta limpia: si subes una versión nueva, archiva la vieja en `memoria/archivo/` o bórrala.

## Archivo de ejemplo

Ya hay un archivo de muestra `EJEMPLO-LEER.md` para que veas el tipo de contenido que va aquí. Puedes borrarlo cuando subas tus propios documentos.
