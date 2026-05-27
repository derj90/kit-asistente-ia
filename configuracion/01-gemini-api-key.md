# Cómo conseguir tu API key de Gemini (gratis)

> Una API key es como una **llave digital** que tu bot necesita para "tocar la puerta" del servicio de IA de Google (Gemini) y pedirle respuestas. Sin esa llave, la IA no le abre la puerta.

> Si vas a construir tu bot solo en gemini.google.com como un Gem, **NO necesitas hacer esto**. Salta a `agentes/`. Esto es solo si vas a usar Codex, Antigravity o cualquier herramienta que conecte por API.

---

## Antes de empezar

**Necesitas**:
- Una cuenta Google activa (institucional o personal).
- Tu navegador habitual con sesión iniciada en esa cuenta.
- 5 minutos.

**No necesitas**:
- Tarjeta de crédito. El plan gratuito es suficiente.
- Conocimiento técnico previo.

---

## Paso a paso

### 1. Entra a Google AI Studio

Abre tu navegador y ve a:

```
https://aistudio.google.com/apikey
```

Inicia sesión con tu cuenta Google si te lo pide.

### 2. Acepta los términos (si aparecen)

La primera vez que entras, Google AI Studio te muestra términos del servicio. Léelos por encima y acepta si estás de acuerdo. Marca también "no, no quiero recibir correos promocionales" si así lo prefieres.

### 3. Crea una API key nueva

Verás un botón azul que dice **"Create API key"** (o "Crear clave de API" si te lo muestra en español).

Haz clic en ese botón.

Te va a preguntar en qué proyecto crear la key. Si nunca has usado Google Cloud, te ofrecerá crear un proyecto nuevo automáticamente: acepta. Si ya tienes proyectos, elige uno o crea uno nuevo con un nombre simple (ej. "mi-asistente-ia").

### 4. Copia la API key INMEDIATAMENTE

Después de unos segundos, te muestra la API key. Es una cadena larga que empieza con `AIzaSy...`.

**Cópiala completa al portapapeles** y pégala en algún lugar seguro de inmediato. Google solo te la muestra una vez; si cierras la ventana sin copiarla, vas a tener que generar una nueva.

> Lugar seguro: NO un correo, NO un chat, NO un documento que vayas a compartir. Idealmente, un gestor de contraseñas (Bitwarden, 1Password) o un archivo local cifrado. Lo más simple para este kit: pégala en el archivo `credenciales.env` que vas a configurar en el siguiente paso.

### 5. Pégala en tu archivo `credenciales.env`

En la carpeta `configuracion/` de este kit, tienes un archivo `credenciales-EJEMPLO.env`. Haz lo siguiente:

1. Copia ese archivo y renómbralo a `credenciales.env` (sin la palabra EJEMPLO).
2. Ábrelo con cualquier editor de texto.
3. Pega tu API key después del signo `=` en la línea `GEMINI_API_KEY=`.
4. Guarda.

Debería quedarte así:

```
GEMINI_API_KEY=AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
```

> El archivo `credenciales.env` está en el `.gitignore` del kit, así que **no se sube por accidente** si versionas con git. Pero igual: nunca lo compartas en correos ni capturas de pantalla.

---

## Cómo verificar que tu key funciona

Tu asistente IA (Codex, Antigravity, Claude Code) puede verificarla por ti. Solo dile:

```
Acabo de pegar mi API key de Gemini en credenciales.env.
¿Puedes verificar que funcione haciendo una llamada de prueba simple?
```

La IA hará una petición mínima a Gemini y te confirmará si la key es válida.

---

## Cuánto puedo usar el plan gratuito

El plan gratuito de Gemini tiene cuotas generosas para uso personal:

- **Gemini 2.5 Flash**: hasta ~15 peticiones por minuto, varios millones de tokens al mes.
- **Gemini 2.5 Pro**: cuotas más restringidas, pero suficientes para experimentar.

Para construir tu primer bot con el kit, **no vas a llegar al límite**. Si trabajas con tu bot construyéndolo y probándolo varias veces al día, sigues estando muy lejos de la cuota gratuita.

> Si en algún momento te aparece un mensaje "quota exceeded", espera unos minutos. Casi siempre es el límite por minuto, no el mensual.

---

## Si algo sale mal

### "No me deja crear la key porque no tengo facturación"
Algunas cuentas Google Workspace institucionales tienen restringido Google AI Studio por política del administrador. Si tu cuenta institucional no funciona:

1. Prueba con tu cuenta Google personal (`@gmail.com`).
2. Si tampoco funciona, consulta con quien administre tu cuenta o pide soporte en el espacio formativo correspondiente.

### "Me pide tarjeta de crédito"
Eso significa que estás en una pantalla equivocada (probablemente Google Cloud Console, no AI Studio). **Cierra**. Vuelve a `https://aistudio.google.com/apikey`. El plan gratuito **no requiere tarjeta**.

### "Perdí mi API key"
Si la perdiste, lo más simple es volver a `https://aistudio.google.com/apikey`, **revocar la key vieja** (botón de basurero) y generar una nueva.

### "Mi key dejó de funcionar"
Verifica que no la hayas pegado mal (sin espacios, sin saltos de línea, completa). Si está bien y aún así no funciona, revócala y genera una nueva.

---

## Recordatorio de seguridad

- Nunca compartas tu API key en correos, chats, capturas, ni código público.
- Si por accidente la publicaste, ve a https://aistudio.google.com/apikey y **revócala** de inmediato.
- Si dejas de usarla, revócala igual. Es una buena higiene digital.

---

¿Listo? Ahora puedes seguir con `02-google-workspace-oauth.md` (si vas por Nivel 2) o ir directo a trabajar tu agente.
