# Mi perfil — Para que tu asistente IA sepa con quién trabaja

> Completa cada bloque con respuestas breves y honestas. Si no sabes alguna, déjala con `[POR COMPLETAR]` y tu asistente IA te ayudará a llenarla cuando converse contigo.

---

## 1. Quién soy

**Nombre**:
[Tu nombre completo]

**Unidad o departamento en UMCE**:
[Ej: Departamento de Educación Diferencial · Facultad de Filosofía y Educación · Coordinación de Postgrado · Secretaría Académica]

**Mi rol en la UMCE**:
[Docente · Coordinador/a académico/a · Jefe/a de carrera · Profesional administrativo/a · Otro: ___]

**Mi nivel de comodidad con tecnología (1-5)**:
[Marca uno: 1 = me cuesta mucho · 2 = sé lo básico · 3 = me defiendo · 4 = me siento cómoda · 5 = experta]

---

## 2. Qué quiero automatizar

**Una tarea que repito una y otra vez en mi semana**:
[Ej: Responder consultas administrativas de estudiantes que se repiten · Redactar comunicados al departamento con formato institucional · Revisar bitácoras de práctica profesional para detectar avances · Resumir transcripciones de reuniones de coordinación · Recordar fechas y enviar correos de seguimiento]

**¿Cuántas veces a la semana hago esta tarea?**:
[Aprox. ___ veces]

**¿Cuánto tiempo me toma cada vez?**:
[Aprox. ___ minutos]

**Lo más tedioso de esa tarea es**:
[Ej: tengo que escribir lo mismo con pequeñas variaciones · tengo que buscar info en varios documentos · tengo que recordar muchos datos · es repetitivo y agotador]

---

## 3. Qué módulo creo que me sirve

> Si no estás segura, déjalo en blanco. Tu asistente IA te ayudará a decidir.

- [ ] **Módulo A — Bot con personalidad** (Gem en Gemini): un asistente conversacional con instrucciones claras. Sin OAuth, sin permisos especiales. Más simple.
- [ ] **Módulo B — Bot orquestador**: un agente que actúa sobre Google Workspace (Calendar, Drive, Gmail, Docs, Sheets) por mí. Requiere configurar OAuth.
- [ ] **Módulo C — Skill propia o conocimiento documental (RAG)**: una rutina encapsulada reusable, o un bot que responde usando mis propios PDFs/documentos.

**Por qué creo que ese módulo me sirve**:
[Tu razonamiento breve]

---

## 4. Qué tengo ya configurado

> Marca lo que ya existe en tu computador o cuentas. Si no tienes algo, no te preocupes — tu asistente IA te guía para conseguirlo.

- [ ] Cuenta Google activa (`@umce.cl` o personal `@gmail.com`).
- [ ] Acceso a https://gemini.google.com (basta con iniciar sesión).
- [ ] Codex (codex.com) o Antigravity (antigravity.com) instalado y con sesión iniciada.
- [ ] API key de Gemini (Google AI Studio). Si no tienes, ver `configuracion/01-gemini-api-key.md`.
- [ ] OAuth Client configurado en Google Cloud Console (**solo si vas por Módulo B**). Ver `configuracion/02-google-workspace-oauth.md`.

---

## 5. Restricciones importantes

**Datos sensibles que NUNCA debo poner en este kit**:
[Lista lo que sea sensible en tu trabajo — nombres y RUTs de estudiantes, evaluaciones, datos médicos, etc. Esto le sirve a tu asistente IA para no incluirlos por accidente en ejemplos]

**Mi plazo de entrega**:
[Grupo 1: domingo 7-jun-2026 · Grupo 2: domingo 2-ago-2026 · ¿Cuál te tocó?]

**Horas que puedo dedicarle a la semana**:
[Aprox. ___ horas]

---

## 6. Una expectativa honesta

**Cuando termine el curso, me gustaría que mi bot pudiera**:
[Una frase. Ej: "responder automáticamente las 5 consultas más frecuentes que me llegan por correo" · "ayudarme a redactar el informe DIDOC mensual en 20 minutos en vez de 2 horas" · "buscar en los syllabus de mi departamento qué profesor enseña qué"]

**Si solo logro X, ya valió la pena**:
[Tu mínimo aceptable. Ej: "solo que el bot entienda mi caso y dé una primera versión razonable"]

---

> Una vez que esto esté completo, abre Codex / Antigravity / Claude Code en esta carpeta y dile: **"Ya completé mi perfil, ayúdame a empezar"**. La IA leerá este archivo + `AGENTS.md` y sabrá exactamente qué hacer contigo.
