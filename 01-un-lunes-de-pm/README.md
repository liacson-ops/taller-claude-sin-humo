# 01 · Un lunes de PM: casilla, calendario y notas

**Tiempo:** 15 minutos · **Herramienta:** [claude.ai](https://claude.ai) (plan gratuito) · **Veredicto:** ✅ sirve, con revisión

## El problema

Es lunes 19 de octubre, 8:40. **Carla Méndez** gestiona el proyecto "TurnoYa" (una app de turnos para la "Clínica Sur") en Nimbus Software. Tiene:

- **22 mails** sin ordenar: un cliente enojado, un hotfix que necesita su OK, facturas, un newsletter de humo…
- **un calendario** que se superpone en varios lugares,
- **tres notas de reunión** con tareas que nadie se asignó.

El jueves hay una demo frente al directorio del cliente. ¿Por dónde empieza?

> Todo es ficticio: empresas, personas, mails y montos.

## Material

| Archivo | Qué es |
|---|---|
| [`casilla.html`](casilla.html) | La bandeja de entrada simulada. Abrila en el navegador y usá **"Copiar toda la casilla como texto"**. |
| [`calendario.html`](calendario.html) | La semana del 19 al 23/10. Botón **"Copiar la semana como texto"**. |
| [`notas/`](notas/) | Tres notas de reunión en texto (daily, reunión con el cliente, refinamiento). |

> Para abrir los `.html`: descargá el repo, hacé doble clic en el archivo y se abre en tu navegador.

## Paso a paso

### Paso 1 · Ordenar la casilla (4')

Abrí `casilla.html`, tocá **Copiar toda la casilla como texto** y pegalo en Claude debajo de este pedido:

```
Soy Carla Méndez, project manager del proyecto TurnoYa en Nimbus Software.
Te pego mi casilla de correo de hoy, lunes 19/10 a las 8:40.

Armá una tabla con todos los mails: número, de quién, asunto,
categoría (Urgente hoy / Importante esta semana / Delegar / Ignorar),
qué tengo que hacer (un verbo + qué), y para cuándo.

Reglas:
- Si el mail no dice una fecha, escribí "sin fecha". No inventes.
- Si un mail depende de otro, decilo.

Al final, decime los 3 que atiendo primero y por qué.
```

### Paso 2 · Revisar el calendario (3')

Abrí `calendario.html`, tocá **Copiar la semana como texto** y pegalo con esto:

```
Este es mi calendario de la semana. Buscá problemas:
- reuniones que se superponen,
- reuniones a las que no llego (por ejemplo, por traslados),
- reuniones donde falta alguien que tiene que estar,
- vencimientos que chocan con otras cosas.

Para cada problema, proponé una solución concreta (mover, delegar, acortar o cancelar).
Usá también lo que sabés de la casilla.
```

### Paso 3 · Sacar tareas de las notas (3')

Copiá el texto de los tres archivos de [`notas/`](notas/) y pegalos con esto:

```
Estas son mis notas de reuniones de los últimos días.
Sacá todas las tareas en una tabla: tarea, responsable, fecha límite y de qué reunión sale.

Marcá con ⚠️ SIN RESPONSABLE las que nadie tomó.
Marcá con ❗ las que contradicen algo de la casilla o del calendario.
```

### Paso 4 · Armar el día (5')

```
Con todo lo anterior, armame el lunes de 9 a 18 en bloques de 30 minutos,
respetando las reuniones del calendario.
Después escribime en borrador los 3 mails más urgentes que tengo que mandar hoy.
Cortos, en tono profesional y cálido.
```

## Qué deberías obtener

- Arriba de todo, el cliente con el problema de iPhone, el OK del hotfix antes de las 16 y el texto para la mesa de ayuda.
- El newsletter "10 prompts…" y la notificación de LinkedIn, en **Ignorar**.
- Al menos 4 problemas de calendario: dos superposiciones del lunes y del martes, la demo presencial pegada a otro evento, y Lucía de licencia el día de la demo y de la planning.
- Varias tareas sin responsable: pedir los logos en alta, la minuta al cliente, las credenciales de la obra social, el resumen de privacidad…
- Una contradicción: Ramiro quiere WhatsApp en la demo, pero eso no está en el alcance.

## Dónde se rompe (revisalo siempre)

- **Fechas y horas.** Si Claude dice "vence el martes", buscá el mail y confirmalo.
- **Lo que no sabe.** No conoce tus prioridades personales ni la política interna. Si algo te parece mal clasificado, decíselo y pedile que rehaga la tabla.
- **Superposiciones.** Verificá en el calendario las que detecta, y fijate si se le pasó alguna.
- **Datos sensibles.** Acá practicamos con datos inventados. Con tu casilla real, no pegues información de clientes en herramientas que tu empresa no aprobó.

## Llevalo a tu trabajo

Elegí 5 mails reales de tu bandeja (sin datos sensibles o anonimizados) y repetí el **Paso 1**. Medí cuánto tardás con y sin Claude.
