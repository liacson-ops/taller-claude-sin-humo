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

## Llevalo a tu trabajo

Elegí el hilo más largo de tu casilla de esta semana (sin datos sensibles) y pedile la tabla. Fijate si encuentra algo que se te había pasado.
