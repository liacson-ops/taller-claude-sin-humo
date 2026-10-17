# 02 · Resumir un hilo de mails en una tabla de decisiones

**Tiempo:** 10 minutos · **Herramienta:** [claude.ai](https://claude.ai) · **Veredicto:** ✅ sirve, con revisión

## El problema

Un hilo de 8 mensajes en 4 días entre el equipo, el comercial y el cliente. Hay decisiones tomadas, una sin confirmar y un riesgo contractual escondido en el mensaje 7. ¿Qué quedó decidido?

## Material

[`hilo.txt`](hilo.txt): el hilo completo (es el mail 15 de la [casilla del ejercicio 01](../01-un-lunes-de-pm/casilla.html)).

## Paso a paso

**1.** Pegá el hilo en Claude con este pedido:

```
Te pego un hilo de mails de un proyecto de software. Armame una tabla con:
- Decisiones tomadas (quién la tomó y en qué mensaje)
- Pendientes (qué falta, quién lo tiene que hacer, para cuándo)
- Riesgos (qué puede salir mal y qué impacto tiene)

Citá el número de mensaje en cada fila. Si algo no está claro en el hilo, ponelo como "sin confirmar".
```

**2.** Pedí la versión para el jefe:

```
Ahora resumilo en 3 líneas para mi jefe, que no leyó nada del hilo.
```

**3.** Pedí la acción que falta:

```
¿Qué mail tendría que mandar yo hoy para cerrar lo que quedó abierto? Escribilo.
```

## Qué deberías obtener

- **Decisión:** en la demo se usa una integración simulada con 3 casos (activo, con deuda, sin cobertura). La real pasa al Sprint 15.
- **Sin confirmar:** que el directorio acepte ver datos de prueba (mensaje 8), y si Lucía llega al ensayo del 21 (mensaje 6).
- **Riesgo clave (mensaje 7):** el contrato dice entrega en producción el 30/10, la fecha real queda en 6/11. Hace falta que el cliente lo acepte **por escrito**.
- **Mail a mandar:** a Ramiro, pidiendo confirmación escrita de la nueva fecha y de los datos de prueba en la demo.

## Dónde se rompe

- **Mezclar quién dijo qué.** Verificá contra el número de mensaje citado.
- **Dar por cerrado lo que no está cerrado.** Si dice "decidido" algo que nadie confirmó, corregilo.
- **Perder el riesgo del mensaje 7.** Si no aparece, preguntá: "¿Hay algún riesgo contractual en el hilo?"

## Ir más lejos: con más datos

Dos hilos más del mismo proyecto y los datos de la mesa de ayuda y del piloto para cruzarlos. Todo es ficticio.

| Archivo | Qué es |
|---|---|
| [`hilo-2-incidente-ios.txt`](hilo-2-incidente-ios.txt) | El chat del equipo durante el incidente del iPhone, del sábado 17 al lunes 19/10 (16 mensajes con horas, cifras, hipótesis y decisiones). |
| [`hilo-3-modulo-facturacion.txt`](hilo-3-modulo-facturacion.txt) | Hilo de 10 mails entre Pedro, Ramiro, Gustavo y Carla para presupuestar el módulo de facturación. |
| [`../datos/mesa-de-ayuda.csv`](../datos/mesa-de-ayuda.csv) | Tickets de pacientes que recibió la mesa de ayuda de la clínica. |
| [`../datos/piloto-turnos.csv`](../datos/piloto-turnos.csv) | Turnos del piloto por día, sede y canal (agosto a octubre). |

**Línea de tiempo del incidente** (pegá `hilo-2-incidente-ios.txt`):

```
Te pego el chat de un equipo durante un incidente.
Armá una línea de tiempo en una tabla: día y hora, quién, qué pasó o qué se decidió.
Después separá:
- hipótesis que se probaron y se descartaron (y con qué evidencia),
- la causa encontrada,
- cada cifra que aparece (tickets, llamadas, turnos), con la hora en que se dijo.
Citá el número de mensaje en cada fila. No completes horas que no estén en el chat.
```

**La misma tabla para los dos hilos nuevos:**

```
Te paso dos hilos: el del incidente del iPhone y el del módulo de facturación.
Para cada uno armá la tabla de decisiones, pendientes y riesgos, como en el paso 1:
quién decidió, en qué mensaje, quién tiene el pendiente y para cuándo.
Si un pendiente no tiene responsable, escribí "SIN RESPONSABLE".
Al final, decime cuál de los dos hilos tiene más riesgo para Nimbus y por qué.
```

**Dashboard del incidente** (subí `hilo-2-incidente-ios.txt`, `../datos/mesa-de-ayuda.csv` y `../datos/piloto-turnos.csv`):

```
Primero decime qué columnas tiene cada CSV y cuántas filas.
Después armame un dashboard interactivo (Artifact) del incidente del iPhone con:
- KPIs arriba: tickets del incidente (iPhone + "Confirmar turno" desde el sábado 17),
  tickets por día y % de turnos confirmados desde la app iOS el 17 y 18/10
  comparado con el promedio de las 4 semanas anteriores;
- un gráfico de tickets por día y por hora del 15 al 19/10, con los hitos del chat marcados
  como líneas verticales (primer reclamo, causa encontrada, decisión del arreglo);
- turnos pedidos y confirmados por día y por canal (App iOS, App Android, Web) de octubre;
- filtros por sede y por canal.
Abajo, una tabla con los totales que usaste, para que los pueda comparar con la planilla.
```

**Compromisos tomados sin consultar:**

```
Revisá los dos hilos nuevos y buscá compromisos que alguien tomó sin consultar al equipo:
fechas, precios, alcances o condiciones que se le prometieron a alguien antes de estimarlos
o de que quien lo tiene que hacer estuviera de acuerdo.
Para cada uno: quién lo dijo, a quién, en qué mensaje, qué consecuencia puede tener
y a quién habría que haber consultado.
Después buscá las fechas que se contradicen entre mensajes.
```

**El mail que ordena el hilo 3:**

```
Con el hilo del módulo de facturación, escribí el mail que Carla le debería mandar a Pedro hoy
para ordenar las fechas y los compromisos antes de que el presupuesto le llegue al cliente.
Tono interno, directo y sin culpar. Máximo 150 palabras.
```

**Dónde se rompe con estos datos:**
- **Las cifras del chat no son la planilla.** En el chat la gente dice números "a ojo" en un momento del día. Compará cada cifra con el CSV y pedile a Claude que separe lo que sale del chat de lo que sale de los datos.
- **Quién le dijo qué a quién.** En el hilo 3 hay mensajes al cliente y mensajes internos. Un compromiso hecho por un mail interno no es lo mismo que uno hecho al cliente: verificá los destinatarios.
- **Fechas parecidas.** Lunes 26, martes 27, jueves 22, viernes 23: revisá cada fecha contra el mensaje que la cita.

## Llevalo a tu trabajo

Elegí el hilo más largo de tu casilla de esta semana (sin datos sensibles) y pedile la tabla. Fijate si encuentra algo que se te había pasado.
