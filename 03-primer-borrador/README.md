# 03 · El primer borrador de un mail difícil

**Tiempo:** 10 minutos · **Herramienta:** [claude.ai](https://claude.ai) · **Veredicto:** ✅ sirve: vos editás, no arrancás de la hoja en blanco

## El problema

El cliente está enojado: los pacientes no pueden confirmar turnos desde iPhone y el jueves presenta el proyecto a su directorio. Hay que responder hoy, sin prometer lo que no se puede cumplir. Además, la mesa de ayuda de la clínica necesita un texto para contestarles a los pacientes.

## Material

Dos mails de la [casilla del ejercicio 01](../01-un-lunes-de-pm/casilla.html):
- **Mail 1:** Ramiro Ibáñez, "URGENTE: los pacientes no pueden confirmar turnos desde iPhone".
- **Mail 20:** Mesa de ayuda, "Pacientes preguntan qué hacer con el turno del iPhone".

Y lo que sabés por el **mail 2**: el arreglo está listo y pasa a producción hoy a las 18 hs si lo aprobás.

## Paso a paso

**1.** El borrador:

```
Necesito responder este mail de un cliente enojado. Te paso el mail y lo que sabemos.

[pegá el mail 1]

Lo que sabemos: el problema es un cambio de Safari en iOS. El arreglo está probado
y pasa a producción hoy a las 18 hs. Mientras tanto, los turnos se pueden confirmar por teléfono.

Escribí una respuesta que:
- reconozca el problema sin excusas ni tecnicismos,
- diga qué pasó en una línea, cuándo se arregla y qué hacer mientras tanto,
- NO prometa nada que no esté en lo que te pasé,
- termine proponiendo una llamada corta hoy.
Máximo 150 palabras.
```

**2.** El tono:

```
Hacelo un poco más cálido y más corto. Sacá cualquier frase que suene a excusa.
```

**3.** El texto para la mesa de ayuda:

```
Ahora escribí el texto que la mesa de ayuda de la clínica le va a mandar a los pacientes
que no pueden confirmar desde iPhone. Simple, amable, 3 líneas, que diga qué hacer hoy.
```

## Qué deberías obtener

Un mail que reconoce, explica en una línea, da hora concreta (hoy 18 hs) y una alternativa (confirmar por teléfono). Y un mensaje para pacientes sin palabras técnicas.

## Dónde se rompe

- **Promesas inventadas.** Revisá que no diga "no va a volver a pasar" ni "compensaremos". No lo dijiste vos.
- **Horarios.** Que diga 18 hs y no otra hora.
- **El último paso es tuyo.** Leelo como si fueras Ramiro antes de mandarlo.

## Ir más lejos: con más datos

Con los hechos verificados y la guía de tono de la empresa, Claude escribe mucho mejor. Todo es ficticio.

| Archivo | Qué es |
|---|---|
| [`contexto-incidente.md`](contexto-incidente.md) | Los hechos verificados del incidente del iPhone: desde cuándo, a cuántos afectó, causa, arreglo, horario y qué decir y qué no. |
| [`guia-de-tono-nimbus.md`](guia-de-tono-nimbus.md) | Cómo le escribe Nimbus a sus clientes y a los pacientes, con frases sí y no. |
| [`mails-dificiles.md`](mails-dificiles.md) | Cinco situaciones más, cada una con destinatario, lo que sabés y lo que no podés decir. |

**Un mail difícil con la guía de tono** (subí `guia-de-tono-nimbus.md` y `mails-dificiles.md`; cambiá el número de situación):

```
Te subo la guía de tono de mi empresa y un archivo con situaciones difíciles.
Escribí el mail de la situación 1, siguiendo la guía al pie de la letra.
- Usá solo los datos de la situación. Si te falta algo, dejalo entre [corchetes].
- Respetá lo que dice "Lo que no podés decir".
- Máximo 150 palabras, con asunto.
Al final, pasá el checklist "Antes de mandar, revisá" de la guía y marcá cada punto.
```

**Antes y después: comparar el tono** (pegá el mail que escribiste en el paso 1 de arriba):

```
Este es un mail que escribí antes de tener la guía de tono. Compará:
1. Una tabla con cada frase que no cumple la guía, qué regla rompe y cómo quedaría.
2. La versión nueva completa.
3. Una tabla "antes / después" con: cantidad de palabras, palabras técnicas,
   fechas con día y hora, próximo paso (sí/no).
No cambies ningún hecho: solo la forma.
```

**Página de estado del incidente para la mesa de ayuda** (subí `contexto-incidente.md` y `guia-de-tono-nimbus.md`):

```
Armame un dashboard interactivo (Artifact) de estado del incidente para la mesa de ayuda de la clínica:
- arriba, 3 indicadores: estado actual (con color), hora del arreglo y qué hacer mientras tanto;
- una línea de tiempo corta con lo que pasó y lo que falta;
- el texto de respuesta para pacientes con un botón "Copiar";
- una sección de preguntas frecuentes desplegables, con buscador (al menos 8 preguntas
  que haría un paciente);
- un recuadro "Qué NO decir" para quien atiende.
Usá solo los hechos de contexto-incidente.md. Lenguaje simple, sin tecnicismos.
Que se vea bien en el celular.
```

**Versión para WhatsApp:**

```
Con los mismos hechos, escribí el mensaje que la clínica le manda por WhatsApp a los pacientes
con iPhone que tienen un turno sin confirmar. Exactamente 3 líneas, sin palabras técnicas,
con el teléfono para confirmar y cuándo vuelve a funcionar la app. Que lo firme la clínica.
Dame dos versiones: una más formal y una más cercana.
```

**Chequeo de hechos del borrador:**

```
Revisá el mail y el texto para pacientes que escribiste contra contexto-incidente.md.
Armá una tabla: cada dato del borrador (fecha, hora, cifra, causa, promesa),
si está en el contexto (sí / no / distinto) y en qué línea.
Marcá todo lo que el contexto pone en "Qué no decir".
```

**Dónde se rompe con estos datos:**
- **Las cifras aproximadas.** El contexto da números redondos con "aprox.". Si el mail dice "57 pacientes" o "todos los turnos", Claude inventó precisión.
- **La guía y la persona.** La guía dice que si te escriben de usted, respondés de usted. Fijate si lo respeta con cada destinatario.
- **Lo que no se puede decir.** En las situaciones difíciles, revisá una por una las frases prohibidas: es lo primero que se le escapa.

## Llevalo a tu trabajo

Pensá en el último mail que te costó escribir. Pasale a Claude los hechos (sin datos sensibles) y pedile el primer borrador. Editalo vos.
