# Rúbrica resumida — Curso 2.4

> Resumen ejecutivo de la rúbrica oficial UDFV. Para la versión completa, ve al programa del curso disponible en el aula virtual eVirtual UMCE.

---

## Aprobación

- **Nota mínima**: 4,0 sobre 7,0.
- **Ponderación**: cada criterio vale 25 % del puntaje total.
- **Modalidad**: producto final + reflexión + pruebas.

---

## Los 4 criterios

### C1 — Pertinencia del caso (25 %)

**Qué se evalúa**: que el caso que elegiste para tu bot esté conectado con tu rol institucional real en UMCE, sea accionable, y resuelva una tarea repetitiva concreta.

| Nivel | Puntaje | Descriptor |
|---|---|---|
| Excelente | 6,5-7,0 | El caso conecta claramente con una tarea repetitiva de tu rol UMCE. Hay evidencia (en perfil + reflexión) de que el bot resuelve un problema real y de que podrías usarlo realmente. |
| Bueno | 5,0-6,4 | El caso es plausible y conectado con tu rol, aunque no del todo aterrizado. |
| Suficiente | 4,0-4,9 | El caso es genérico o poco vinculado a tu rol específico; aún así, hay un esbozo de aplicación posible. |
| Insuficiente | < 4,0 | El caso es claramente desconectado de tu rol UMCE o no se entiende por qué te serviría. |

**Cómo se evidencia**: en `mi-perfil.md` (completado con datos reales) + en la introducción de `entregable/reflexion.md`.

---

### C2 — Solidez técnica del bot (25 %)

**Qué se evalúa**: que el system prompt o la configuración del agente que construiste sea sólida, tenga los 4 componentes claros (rol / estilo / criterios / restricciones), tenga suficiente densidad, y refleje decisiones técnicas pensadas.

| Nivel | Puntaje | Descriptor |
|---|---|---|
| Excelente | 6,5-7,0 | System prompt mínimo 300 palabras, los 4 componentes claramente identificables, restricciones explícitas (≥3 reglas duras), evidencia de iteración (versiones documentadas), elección justificada de herramienta. |
| Bueno | 5,0-6,4 | System prompt sólido con los 4 componentes presentes; las restricciones son adecuadas aunque no exhaustivas. |
| Suficiente | 4,0-4,9 | System prompt cubre lo mínimo; alguno de los 4 componentes está débil. |
| Insuficiente | < 4,0 | System prompt menor a 200 palabras, falta uno o más componentes, o las restricciones son inexistentes. |

**Cómo se evidencia**: en `entregable/system-prompt-final.md`.

---

### C3 — Calidad de las conversaciones de prueba (25 %)

**Qué se evalúa**: que probaste tu bot con al menos un caso típico (dentro de su rol) y un caso límite (fuera de rol), y que las pruebas muestran que el bot responde con la calidad que definiste.

| Nivel | Puntaje | Descriptor |
|---|---|---|
| Excelente | 6,5-7,0 | Al menos 2 conversaciones de prueba bien documentadas (típica + borde), análisis breve tuyo de cada una, evidencia clara de que el bot cumple criterios definidos en el system prompt, datos anonimizados. |
| Bueno | 5,0-6,4 | 2 pruebas presentes, análisis básico, datos anonimizados. |
| Suficiente | 4,0-4,9 | Al menos 1 prueba documentada, sin mucho análisis pero con evidencia mínima de que el bot responde. |
| Insuficiente | < 4,0 | Sin pruebas, o pruebas sin documentar, o con datos sensibles expuestos. |

**Cómo se evidencia**: en `entregable/capturas/` (transcripciones .md o capturas .png con notas).

---

### C4 — Profundidad de la reflexión (25 %)

**Qué se evalúa**: que tu reflexión escrita articule el caso, los límites éticos detectados, los ajustes que hiciste durante la construcción, y tu lectura honesta sobre si vas a usar el bot realmente.

| Nivel | Puntaje | Descriptor |
|---|---|---|
| Excelente | 6,5-7,0 | Reflexión de 200-400 palabras que articula los 4 ejes (caso + iteración + ética + proyección), identifica un límite ético específico de tu rol, propone una política concreta para el bot, y es honesta en la proyección. |
| Bueno | 5,0-6,4 | Reflexión presente y articulada, cubre los 4 ejes aunque algunos sin profundizar. |
| Suficiente | 4,0-4,9 | Reflexión cumple lo mínimo (200 palabras), toca al menos 2 de los 4 ejes. |
| Insuficiente | < 4,0 | Reflexión menor a 150 palabras, o no toca límites éticos, o es decorativa (frases hechas sin aterrizaje). |

**Cómo se evidencia**: en `entregable/reflexion.md`.

---

## Cómo se calcula tu nota

Promedio simple de los 4 criterios:

```
Nota final = (C1 + C2 + C3 + C4) / 4
```

Aprobación con nota final ≥ 4,0.

---

## Lo que NO se evalúa (relájate)

- **Estética del bot**: no importa si tu bot tiene "buena onda" decorativa. Lo que importa es que sirva.
- **Complejidad técnica**: un Gem simple bien hecho saca mejor nota que un orquestador a medio terminar.
- **Volumen de trabajo**: 4 horas bien gastadas valen más que 20 horas dispersas.
- **Perfección**: la rúbrica valora iteración (que muestres que ajustaste cosas). No esperan un producto perfecto al primer intento.

---

## Si tu nota va a quedar baja por algún criterio

Si te das cuenta que te falta evidencia en algún criterio, **prioriza**:

1. **Prioridad 1**: tener el `system-prompt-final.md` completo con los 4 componentes (C2).
2. **Prioridad 2**: tener al menos 1 conversación de prueba documentada (C3).
3. **Prioridad 3**: tener una reflexión mínima de 200 palabras tocando ética + proyección (C4).
4. **Prioridad 4**: rellenar bien `mi-perfil.md` para que el caso quede claro (C1).

Si hiciste 1, 2 y 3, ya tienes pasaje seguro a la aprobación. La pertinencia (C1) se evidencia naturalmente si la reflexión está bien hecha.
