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

## Ir más lejos: con más datos

Con 8 posts se aprende la prueba. Con 30 y sus números se ve el negocio del humo: qué recibe más likes y qué se guarda para usar después.

| Archivo | Qué es |
|---|---|
| [`posts.md`](posts.md) | Los posts 1 a 8 del ejercicio base. |
| [`posts-extra.md`](posts-extra.md) | Posts 9 a 30, inventados: LinkedIn, Instagram, X y descripciones de TikTok. Hay humo, posts útiles y algunos que dan para discutir. |
| [`posts-metricas.csv`](posts-metricas.csv) | Una fila por post (1 a 30): red, formato, likes, comentarios, compartidos, guardados y 5 señales marcadas a mano (si/no): `pide_comentar`, `cita_fuente`, `muestra_proceso`, `promete_resultado`, `menciona_tarea_concreta`. **Todos los números son ficticios.** |

**1. Clasificar los 30:**

```
Te paso 30 posts de redes sobre IA (dos archivos, la numeración sigue del 1 al 30).
Evaluá cada uno con estas 4 preguntas:
1. ¿Dice qué tarea concreta mejora?
2. ¿Tiene una fuente que se pueda abrir?
3. ¿Muestra el proceso o solo el resultado?
4. ¿Pide algo a cambio (comentar, seguir, comprar, compartir)?

Dame una tabla: post, red, las 4 respuestas (sí/no), veredicto (SIRVE, A MIRAR o HUMO)
y una frase que justifique el veredicto. Marcá con "dudoso" los posts donde la regla
"falla 2 o más = HUMO" te da un resultado que no te convence, y explicá por qué.
[adjuntá posts.md y posts-extra.md]
```

**2. Cruzar el veredicto con los números:**

```
Ahora te paso posts-metricas.csv. Sumale a cada post el veredicto de la tabla anterior.
Calculá, por veredicto: cantidad de posts, promedio de likes, comentarios, compartidos y guardados,
y la proporción guardados/likes. Repetí el cálculo solo para LinkedIn, para ver si la conclusión
se sostiene dentro de una misma red. Decime en 3 líneas qué muestran los números
y cuáles son las excepciones (posts que no siguen el patrón).
[adjuntá posts-metricas.csv]
```

**3. El dashboard "humo vs likes":**

```
Armame un dashboard interactivo (Artifact) con los 30 posts, sus métricas y el veredicto
que acordamos. Quiero:
- Arriba, 4 KPIs: cantidad de posts por veredicto, likes promedio del HUMO vs. de lo que SIRVE,
  guardados promedio de cada uno, y la proporción guardados/likes por veredicto.
- Un gráfico de barras agrupadas: likes, comentarios, compartidos y guardados promedio por veredicto.
- Un gráfico de dispersión: likes (eje X) vs. guardados (eje Y), un punto por post,
  coloreado por veredicto, con el número de post al pasar el mouse.
- Un ranking (tabla ordenable) de los 30 posts por likes, con columnas de veredicto y red.
- Filtros por red (LinkedIn, Instagram, X, TikTok) y por formato que actualicen todo.
Que se lea bien en el celular y que los colores no dependan solo del rojo/verde.
```

**4. Del humo a algo útil:**

```
Elegí los 3 posts HUMO con más likes y reescribí cada uno en versión útil:
qué tarea concreta, qué se probó, qué resultado con número, dónde falló y qué fuente se puede abrir.
Si para eso falta información que el post no tiene, no la inventes: dejá [completar] en su lugar.
Máximo 4 líneas cada uno.
```

**5. Tu propio checklist:**

```
Con lo que vimos en los 30 posts, ayudame a armar mi checklist personal para decidir
si comparto un post de IA. Máximo 6 preguntas de sí/no, ordenadas de la más rápida a la más lenta,
y para cada una un ejemplo de los 30 posts que la falla. Al final, una versión de una línea
para tener pegada en el escritorio.
```

**Dónde se rompe (con estos datos):**

- **Las señales del CSV son una opinión.** `cita_fuente` o `muestra_proceso` las marcó una persona. Si Claude clasifica copiando esas columnas en vez de leer el post, el ejercicio pierde sentido: pedile que clasifique primero y cruce después.
- **30 posts no son una estadística.** Sirven para ver un patrón, no para afirmar "el humo tiene 3 veces más likes" en un informe. Y los números son inventados.
- **Revisá los promedios del dashboard** contra la planilla (sumá a mano una categoría). Y fijate que el filtro por red cambie también los KPIs, no solo los gráficos.

## Llevalo a tu trabajo

Esta semana, antes de compartir un post de IA, pasalo por las 4 preguntas. Y si escribís sobre IA, pasá vos la prueba.
