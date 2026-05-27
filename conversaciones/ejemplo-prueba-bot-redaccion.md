# Prueba — Caso típico, asistente de redacción

**Bot**: Asistente Redacción UMCE (Gem en gemini.google.com)
**Modelo**: Gemini 2.5 Flash
**Temperatura**: 0,3
**Fecha**: 27-05-2026
**Tipo de caso**: Típico (dentro del dominio del bot)

---

## Lo que le pedí

> Tengo que comunicarle al equipo docente de Pedagogía en Música que se cambió la sala del Consejo de Departamento del jueves 5 de junio: era la sala A-201 y ahora es la C-104, misma hora (15:00). Redacta el correo.

## Lo que respondió

> Entiendo que necesitas comunicar al equipo docente de Pedagogía en Música el cambio de sala del Consejo de Departamento del 5 de junio: de A-201 a C-104, manteniendo la hora (15:00). Te paso un borrador:
>
> ---
>
> **Asunto**: Cambio de sala — Consejo de Departamento jueves 5 de junio
>
> Estimadas, estimados colegas:
>
> Les escribo para informar un cambio en la sala donde se realizará el Consejo de Departamento del próximo jueves 5 de junio. La sesión se trasladará desde la sala A-201 a la sala C-104, manteniendo el horario habitual a las 15:00.
>
> Les recordamos llegar con algunos minutos de anticipación. La C-104 se encuentra [pendiente confirmar: edificio y piso].
>
> Quedamos atentas a cualquier consulta.
>
> Saludos cordiales,
>
> [Nombre · Coordinación · Pedagogía en Música · UMCE]
>
> ---
>
> Si te sirve, te ofrezco dos ajustes alternativos:
>
> 1. **Versión más breve** para WhatsApp del equipo: "Recordatorio: el Consejo del jueves 5 cambia de sala. Ahora es la C-104, misma hora (15:00). Saludos."
> 2. **Versión más formal**, si va a autoridades externas o invitados al Consejo: cambio el tratamiento por "Estimadas y estimados colegas" + cierre "Atentamente,".
>
> ¿Te sirve este borrador, o ajustamos algo?

## Mi lectura

Salió bien. El bot:

- Parafraseó la solicitud en la primera línea (criterio 1 del system prompt — confirmado).
- Pidió que confirme un dato que le faltaba (edificio y piso de la C-104) sin inventárselo (criterio 3 — confirmado).
- Estructuró el correo según el formato pedido (saludo, contexto, mensaje, próximos pasos, firma como placeholder).
- Ofreció dos ajustes alternativos al final (criterio 5 — confirmado).
- Mantuvo registro formal-cercano sin signos de exclamación ni emojis.

**Lo que no fue perfecto**: el tratamiento "Estimadas, estimados colegas" me sonó un poco rígido. En la siguiente iteración del system prompt, podría afinar el bloque ESTILO para que use "Estimado equipo" o algo más cercano cuando es comunicación interna.

**Ajuste pendiente para v0.2**: agregar al bloque ESTILO una línea: "Para comunicaciones internas al propio equipo del usuario, prefiere 'Estimado equipo' o 'Hola a todas y todos'; reserva 'Estimadas/estimados colegas' para invitados externos."
