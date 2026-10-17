# 06 · Detectar el contenido "bait" que pide likes sin decir nada

**Tiempo:** 15 minutos · **Herramienta:** [claude.ai](https://claude.ai) + tu criterio · **Veredicto:** el ejercicio es aprender a dar el veredicto

## El problema

Todos los días el feed te promete que la IA "lo cambia todo". Algunos posts informan; otros solo buscan reacciones. Aprender a distinguirlos ahorra tiempo y evita decisiones basadas en humo.

## La prueba en 4 preguntas

Antes de creer o compartir un post sobre IA:

1. **¿Dice qué tarea concreta mejora?** "Lo cambia todo" no es una tarea.
2. **¿Tiene una fuente que puedas abrir?** Un anuncio oficial, un estudio con autor. "Un estudio revela" no cuenta.
3. **¿Muestra el proceso o solo el resultado?** "Gané USD 12.000" sin el cómo es un anzuelo.
4. **¿Te pide algo a cambio?** Comentar, seguir, comprar "solo hoy".

Veredictos: **SIRVE** (pasa la prueba) · **A MIRAR** (es real pero le falta algo) · **HUMO** (falla 2 o más).

## Material

[`posts.md`](posts.md): 8 posts inventados, mezclados.

## Paso a paso

**1. Primero vos (5').** Leé los 8 posts y anotá tu veredicto en cada uno, sin IA.

**2. Después Claude:**

```
Te paso 8 posts de redes sobre IA. Evaluá cada uno con estas 4 preguntas:
1. ¿Dice qué tarea concreta mejora?
2. ¿Tiene una fuente verificable?
3. ¿Muestra el proceso o solo el resultado?
4. ¿Pide algo a cambio (comentar, comprar, seguir)?

Dame una tabla con las 4 respuestas y un veredicto: SIRVE, A MIRAR o HUMO.
[pegá posts.md]
```

**3. Compará.** ¿En cuáles no coincidieron? Discutilo: ahí está el aprendizaje.

**4. Reescribí uno:**

```
Reescribí el post 1 para que diga algo útil y verificable, sin exagerar. Máximo 3 líneas.
```

## Qué deberías obtener

- **HUMO:** 1, 2, 4, 6 y 7.
- **SIRVE:** 3 y 8 (dicen qué probaron, cuánto sirvió y dónde falló).
- **A MIRAR:** 5, que es real y tiene fuente, pero hay que abrir el anuncio para confirmarlo.

## Dónde se rompe

- **La IA tampoco puede verificar la fuente** si no la abre. Que un post cite "el anuncio oficial" no significa que exista: hacé clic vos.
- **El tono no alcanza.** Un post serio puede ser falso y uno informal puede ser útil. Por eso son 4 preguntas y no "suena exagerado".

## Llevalo a tu trabajo

Esta semana, antes de compartir un post de IA, pasalo por las 4 preguntas. Y si escribís sobre IA, pasá vos la prueba.
