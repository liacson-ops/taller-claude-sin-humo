# 05 · Preparar una reunión: agenda, preguntas y objeciones

**Tiempo:** 10 minutos · **Herramienta:** [claude.ai](https://claude.ai) · **Veredicto:** ✅ sirve: te hace las preguntas antes que el directorio

## El problema

El jueves Carla presenta el proyecto al directorio del cliente. Hay cosas que funcionan, cosas que no conviene mostrar, un cambio de fecha que el contrato no contempla y dos directores con preguntas difíciles.

## Material

[`contexto.md`](contexto.md): todo lo que sabemos de la reunión. Sale de la casilla, el calendario y las notas del ejercicio 01.

## Paso a paso

**1.** La agenda:

```
Voy a presentar un proyecto de software al directorio de un cliente. Te paso el contexto.
[pegá contexto.md]

Armá una agenda de 60 minutos con tiempos, qué se muestra en cada parte y quién lo presenta.
Dejá 15 minutos para preguntas.
```

**2.** Las preguntas difíciles:

```
Ahora hacé de cada director: la Directora médica y el Director financiero.
¿Qué 5 preguntas difíciles me harían? Para cada una, dame una respuesta corta y honesta
basada SOLO en el contexto. Si el contexto no alcanza para responder, decímelo.
```

**3.** El plan B:

```
¿Qué puede salir mal durante la demo en vivo y qué hago en cada caso?
```

**4.** El cambio de fecha:

```
¿Cómo comunico en la reunión que la integración real llega el 6/11 y no el 30/10,
sin que suene a excusa? Dame 2 frases posibles.
```

## Qué deberías obtener

- Una agenda que **no** muestra reprogramar turnos y que explica la integración simulada desde el principio.
- Preguntas de la Dra. Ríos sobre dónde se guardan los datos y quién accede. Claude debería decir que el contexto **no** tiene esa información: hay que pedírsela a Juan.
- Preguntas del Cdor. Paz sobre el costo anual. El soporte figura "a confirmar": no conviene dar un número cerrado.
- Un plan B para la conexión, los datos de prueba y el iPhone.

## Dónde se rompe

- **Respuestas inventadas.** Si responde sobre privacidad con detalles técnicos que no le diste ("los datos se cifran con…"), es **humo**: no lo sabe. Pedile que marque qué es supuesto.
- **Tono.** Ensayalo en voz alta: lo que suena bien escrito a veces suena raro dicho.

## Ir más lejos: con más datos

Con más contexto, Claude puede ayudarte a preparar los materiales de la reunión, ensayar las preguntas difíciles y llevar los números del piloto en un tablero. Todo es ficticio.

| Archivo | Qué es |
|---|---|
| [`perfiles-directorio.md`](perfiles-directorio.md) | Ramiro, la Dra. Ríos y el Cdor. Paz: qué les importa, cómo deciden, qué objetaron antes y frases que dijeron en reuniones anteriores. |
| [`minuta-reunion-anterior.md`](minuta-reunion-anterior.md) | Minuta del kickoff con el directorio (abril 2026): alcance, metas del piloto y compromisos con responsable y fecha. |
| [`privacidad-preguntas-frecuentes.md`](privacidad-preguntas-frecuentes.md) | Lo que respondió Juan sobre dónde están los datos, cifrado, accesos, retención y consentimiento. Tiene puntos marcados "a confirmar con legal". |
| [`costos-mantenimiento.md`](costos-mantenimiento.md) | Borrador del costo mensual y anual de mantener TurnoYa en 2027, con supuestos. |
| [`../datos/piloto-turnos.csv`](../datos/piloto-turnos.csv) | Turnos por día, sede y canal (app iOS, app Android, web, teléfono y presencial) en las 3 sedes del piloto, con las llamadas a recepción. Del 01/08 al 18/10/2026. Datos ficticios. |
| [`../datos/encuesta-pacientes.csv`](../datos/encuesta-pacientes.csv) | 150 respuestas de la encuesta a pacientes del piloto: puntaje de 0 a 10 (NPS), facilidad de uso, sede, plataforma, rango de edad y comentario. Datos ficticios. |

**1. El one-pager para el directorio**

```
Te paso el contexto de una reunión con el directorio de un cliente y varios archivos:
contexto.md, minuta-reunion-anterior.md, privacidad-preguntas-frecuentes.md
y costos-mantenimiento.md.
Armá un one-pager (una sola página, para imprimir) para el directorio con:
- qué prometimos en el kickoff y qué cumplimos, con números
- qué no cumplimos y cuándo lo vamos a cumplir
- privacidad en 5 líneas, sin tecnicismos, con lo que está "a confirmar" marcado como tal
- costo anual con la cuenta resumida
- próximos pasos con responsable y fecha
Usá solo datos de los archivos. Si algo no está, poné "a definir", no lo inventes.
```

**2. El guion de la demo, minuto a minuto**

```
Con contexto.md y perfiles-directorio.md, armá el guion de una demo en vivo de 20 minutos
dentro de la reunión de 60. Minuto a minuto: qué se muestra en pantalla, qué se dice
(frase textual), quién habla (Carla o Juan) y qué pregunta del directorio puede aparecer ahí.
Reglas:
- No mostrar nada de lo que el contexto dice que no conviene mostrar.
- Si alguien pide ver eso en vivo, dame la frase para responder.
- La integración con la obra social se explica ANTES de mostrarla, no después.
- Cerrá con los números del piloto.
```

**3. Ensayo de objeciones (role-play)**

```
Vamos a ensayar. Leé perfiles-directorio.md, privacidad-preguntas-frecuentes.md
y costos-mantenimiento.md. Hacé de la Dra. Elena Ríos: hacé UNA pregunta difícil por vez,
con su forma de hablar, y esperá mi respuesta. Después de cada respuesta mía:
- decime en una línea si me creería y por qué
- marcá si dije algo que no está en los archivos
- seguí con una repregunta o con la próxima pregunta.
Después de 5 preguntas, cambiá al Cdor. Gustavo Paz y hacé lo mismo con los costos.
Al final, dame las 3 respuestas que más tengo que mejorar.
```

**4. Dashboard del piloto para mostrar en la demo**

```
Armame un dashboard interactivo (Artifact) con los resultados del piloto de TurnoYa
para mostrar al directorio, usando ../datos/piloto-turnos.csv y ../datos/encuesta-pacientes.csv.
- KPIs arriba: turnos pedidos por la app en septiembre, % de adopción de la app
  sobre el total de turnos, variación de llamadas a recepción septiembre contra agosto, y NPS.
- Barras apiladas: turnos por sede (Caballito, Flores, Almagro) y por canal.
- Líneas por semana: evolución de turnos por la app y de turnos por teléfono, de agosto a octubre.
- NPS: distribución de puntajes de 0 a 10 con promotores, pasivos y detractores en colores
  distintos, y NPS por sede.
- 5 comentarios textuales de pacientes: los más representativos, positivos y negativos.
- Filtros por sede y por mes.
Mostrame cómo calculaste cada KPI en una nota al pie. No inventes columnas que no están en los CSV.
```

**5. El costo anual, con la cuenta a la vista**

```
Con costos-mantenimiento.md, calculá el costo anual de mantener TurnoYa.
Mostrame cada suma paso a paso, separá lo confirmado de lo estimado y de lo "a confirmar",
y armá dos escenarios:
- soporte $ 650.000 por mes con IVA incluido, sin ajustes de precio
- soporte $ 650.000 más IVA y un ajuste del hosting de 8 % cada tres meses a partir del segundo trimestre
Dame la tabla final como se la mandaría al Cdor. Paz: simple, mensual y anual.
Si el resultado no coincide con el total del archivo, decime dónde está la diferencia.
```

**6. Rendir cuentas de la reunión anterior**

```
Con minuta-reunion-anterior.md y contexto.md, armá una tabla con cada compromiso del kickoff:
compromiso, responsable, fecha, estado (cumplido, no cumplido, no sé) y la evidencia.
Si los archivos no alcanzan para saber el estado, poné "no sé" y decime a quién preguntarle.
Para cada compromiso no cumplido, dame una frase honesta para decirlo en la reunión.
```

**Dónde se rompe con más datos**

- **El dashboard no coincide con el contexto.** El contexto dice 1.240 turnos por la app en septiembre y 31 % menos llamadas. Si el dashboard muestra otros números, revisá qué filtró (fechas, canales, sedes) antes de llevarlo al directorio.
- **NPS mal calculado.** NPS no es el promedio de los puntajes: es % de promotores (9 y 10) menos % de detractores (0 a 6). Pedile que muestre la cuenta.
- **Lo "a confirmar" se vuelve un hecho.** En el one-pager y en el role-play, fijate que lo marcado "a confirmar" en privacidad y en costos siga diciendo "a confirmar". Y que el costo anual no sea solo hosting + soporte × 12.

## Llevalo a tu trabajo

Elegí tu próxima reunión importante. Escribí 10 líneas de contexto (sin datos sensibles) y repetí el paso 2.
