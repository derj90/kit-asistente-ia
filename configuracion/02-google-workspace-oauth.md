# Cómo conectar tu bot con Google Workspace (OAuth)

> **OAuth** es el sistema mediante el cual le das permiso a una aplicación (tu bot) para que acceda a algunos de tus servicios Google (Calendar, Drive, Gmail, Docs, Sheets) en tu nombre, **sin entregarle tu contraseña**. Es como una credencial de visita: la aplicación entra, hace lo que le autorizaste, y nada más.

> **Solo necesitas hacer esto si vas por Módulo B (Bot orquestador con Workspace).** Si vas por Módulo A o C, salta este archivo.

---

## Antes de empezar — Decisión importante: qué cuenta usar

Tienes que decidir con qué cuenta Google vas a configurar OAuth:

| Opción | Cuándo te conviene |
|---|---|
| **Cuenta UMCE `@umce.cl`** | Si tu bot va a tocar Drive/Calendar/Gmail **institucionales** (ej. agendar reuniones de tu equipo, leer correos UMCE). |
| **Cuenta personal `@gmail.com`** | Si quieres practicar sin riesgo de tocar datos institucionales, o si tu cuenta institucional tiene restricciones por política del administrador. |

**Recomendación UDFV**: para este curso, **usa tu cuenta personal**. Una vez que el bot esté funcionando y comprobado, puedes migrarlo a `@umce.cl`. Así evitas tocar datos institucionales mientras aprendes.

---

## Antes de empezar — Lo que necesitas

- 30-45 minutos.
- Tu navegador con sesión iniciada en la cuenta Google que elegiste arriba.
- Paciencia: el panel de Google Cloud Console tiene muchos botones; si te pierdes, dile a tu asistente IA "estoy en la pantalla X de OAuth, ¿qué hago?".

---

## Paso a paso

### 1. Entra a Google Cloud Console

Abre tu navegador y ve a:

```
https://console.cloud.google.com/
```

Inicia sesión con la cuenta que elegiste.

### 2. Crea un proyecto (o usa uno existente)

Arriba a la izquierda, junto al logo de Google Cloud, verás un selector de proyecto. Haz clic.

- Si no tienes ningún proyecto, te ofrecerá crear uno: dale un nombre simple como `curso-2-4-bot`.
- Si ya tienes proyectos (porque generaste API key Gemini antes), puedes reutilizar el mismo proyecto.

Espera unos segundos a que se cree.

### 3. Activa las APIs que tu bot va a usar

En el menú izquierdo (las 3 líneas arriba a la izquierda), busca **"APIs y servicios" → "Biblioteca"**.

Activa las APIs que necesitas según tu caso. Para cada una: buscas su nombre, haces clic, y aprietas el botón azul **"Habilitar"**.

| Necesitas que tu bot... | API que debes habilitar |
|---|---|
| Lea/cree archivos en Drive | **Google Drive API** |
| Lea/cree eventos en Calendar | **Google Calendar API** |
| Lea/redacte correos en Gmail | **Gmail API** |
| Lea/edite documentos en Docs | **Google Docs API** |
| Lea/edite planillas en Sheets | **Google Sheets API** |

> Habilita solo las que vas a usar. Si después necesitas más, vuelves y las habilitas en ese momento.

### 4. Configura la "Pantalla de consentimiento"

En el menú izquierdo: **"APIs y servicios" → "Pantalla de consentimiento de OAuth"**.

La primera vez te pedirá elegir tipo de usuario:

- **Interno**: solo si tu cuenta es Google Workspace de una organización. Si usas `@umce.cl` y la UMCE lo permite, esta es la opción más simple.
- **Externo**: para cuentas `@gmail.com` o si la opción interna no aparece. Tu app queda en "modo prueba" hasta que la publiques. Está bien, no necesitas publicarla para el curso.

Después te pide rellenar:

- **Nombre de la app**: pon algo descriptivo, ej. "Mi Asistente Curso 2.4".
- **Correo de soporte de usuario**: tu propio correo.
- **Dominios autorizados**: déjalo vacío para uso personal.
- **Información de contacto del desarrollador**: tu correo.

Guarda y avanza.

Luego te pide **scopes** (permisos específicos). Aquí agregas los permisos exactos que tu bot necesita:

| Scope | Para qué sirve |
|---|---|
| `https://www.googleapis.com/auth/calendar` | Leer y modificar eventos del calendario |
| `https://www.googleapis.com/auth/drive` | Leer y modificar archivos en Drive |
| `https://www.googleapis.com/auth/drive.file` | Solo los archivos que tu app crea (más restrictivo, más seguro) |
| `https://www.googleapis.com/auth/gmail.send` | Enviar correos (con confirmación humana siempre) |
| `https://www.googleapis.com/auth/gmail.compose` | Redactar borradores (más seguro que enviar) |
| `https://www.googleapis.com/auth/gmail.readonly` | Solo leer correos (muy útil para clasificar/buscar) |
| `https://www.googleapis.com/auth/documents` | Leer y modificar Google Docs |
| `https://www.googleapis.com/auth/spreadsheets` | Leer y modificar Google Sheets |

> **Recomendación UDFV de seguridad**: usa siempre el scope más restrictivo que aún te sirva. Por ejemplo, si vas a clasificar correos sin enviarlos, usa `gmail.readonly`. Si vas a redactar borradores pero quieres revisarlos antes de enviar, usa `gmail.compose` (no `gmail.send`). **Nunca actives `gmail.send` salvo que sea estrictamente necesario** — y aún así, tu bot debe estar configurado para pedirte confirmación humana antes de cada envío.

Después de agregar los scopes, sigue avanzando hasta terminar la configuración de la pantalla de consentimiento. Si estás en "modo prueba" (externo), agrega tu propio correo como "usuario de prueba" antes de terminar.

### 5. Crea el OAuth Client ID

En el menú izquierdo: **"APIs y servicios" → "Credenciales"**.

Arriba, haz clic en **"+ Crear credenciales" → "ID de cliente de OAuth"**.

Te pide tipo de aplicación. Elige según tu herramienta:

- **Aplicación de escritorio** → si vas a usar Codex, Antigravity o Claude Code en tu computador.
- **Aplicación web** → si configurarás algo que corre en un servidor.

Para el Curso 2.4 lo normal es **Aplicación de escritorio**. Dale un nombre descriptivo (ej. "Cliente Curso 2.4 Bot") y crea.

Te muestra:
- **Client ID** (cadena que termina en `.apps.googleusercontent.com`).
- **Client Secret** (cadena más corta, alfanumérica).

**Cópialos al portapapeles** y pégalos en tu archivo `credenciales.env`:

```
GOOGLE_OAUTH_CLIENT_ID=123456789-abc...xyz.apps.googleusercontent.com
GOOGLE_OAUTH_CLIENT_SECRET=GOCSPX-AbcDef...
```

> El Client Secret es tan sensible como una contraseña. **No lo compartas ni lo subas a GitHub.**

### 6. Descarga el archivo JSON (opcional pero útil)

En la misma pantalla, junto a tu cliente recién creado, hay un ícono de descarga. Descarga el JSON y guárdalo en una carpeta segura. Algunas herramientas piden este JSON en vez del Client ID/Secret por separado.

### 7. Verifica que todo esté listo

Le dices a tu asistente IA:

```
Ya configuré OAuth en Google Cloud Console y pegué Client ID + Secret
en credenciales.env. Mis scopes habilitados son: [lista los scopes].
¿Puedes verificar que el flujo OAuth funcione haciendo una llamada de prueba?
```

Tu asistente IA lanzará una autorización OAuth. Eso abrirá tu navegador, te pedirá iniciar sesión con la cuenta que configuraste, y te mostrará la pantalla de consentimiento (los scopes que pediste). Aceptas, y la IA confirma que el flujo funciona.

---

## Si algo sale mal

### "Acceso denegado" o "App no verificada"
Si estás en "modo prueba" (cuenta externa), tienes que agregar tu propio correo como **usuario de prueba** en la pantalla de consentimiento. Si no lo hiciste en el paso 4, vuelve y agrégalo.

### "Redirect URI mismatch"
Significa que tu herramienta está pidiendo OAuth con una URL de retorno distinta a la que registraste. La solución más simple: en la pantalla del Client ID, agrega la URL exacta que la herramienta te dice (suele empezar con `http://localhost:` algún puerto).

### "Scope inválido" o "scope not enabled"
Significa que pediste un scope para una API que no habilitaste. Vuelve a "Biblioteca" y habilita esa API.

### "Quota exceeded"
Las APIs Google tienen cuotas generosas en plan gratuito. Si alcanzas la cuota probando, espera unos minutos. Si pasa seguido, hay algo mal configurado — pregúntale a tu IA.

### Te sientes perdida
Pega capturas de tu pantalla actual al chat con tu asistente IA, y dile "estoy aquí, ¿qué hago?". Casi siempre va a poder orientarte sin que tengas que reiniciar.

---

## Política de uso seguro de OAuth — Léela antes de usar tu bot

Una vez configurado OAuth, tu bot técnicamente puede:
- Crear, modificar y borrar eventos de Calendar.
- Leer, modificar y borrar archivos de Drive.
- Enviar correos en tu nombre (si activaste `gmail.send`).
- Leer todos tus correos (si activaste `gmail.readonly`).

**Recomendaciones obligatorias UDFV**:

1. **Antes de cualquier acción destructiva** (borrar evento, eliminar archivo, mover algo importante), tu bot debe pedirte confirmación explícita: "¿Quieres que borre el evento X del 5 de junio? Responde sí o no."
2. **Nunca configurar el bot para enviar correos automáticamente**. Que siempre **redacte como borrador** y te avise: "El borrador está listo en tu bandeja de borradores; revísalo y envíalo manualmente."
3. **Nunca pongas el bot a procesar correos masivamente sin revisión humana**. Funciona muy bien clasificando; pero las respuestas siempre las revisas tú.
4. **Si vas a leer correos**, prefiere el scope `gmail.readonly` antes que cualquier scope que también permita escribir.
5. **Si terminó el curso y ya no usas el bot**, vuelve a Google Cloud Console y borra el Client ID. Las credenciales que no se usan son riesgo gratis.

---

## Revocar acceso después del curso

Si quieres quitar todos los permisos que diste:

1. Ve a https://myaccount.google.com/permissions
2. Busca "Mi Asistente Curso 2.4" (o como hayas llamado a tu app).
3. Haz clic → **"Quitar acceso"**.

Esto invalida todos los tokens de tu bot sin que tengas que borrar el Client ID en Cloud Console.
