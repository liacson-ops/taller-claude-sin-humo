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

## Ir más lejos: con más datos

Más notas, el reporte de estado de la semana pasada y los datos del proyecto con **puntos de historia**. Todo es ficticio. Los `.csv` están en la carpeta [`datos/`](../datos/): subilos a Claude con el clip o arrastrándolos al chat.

| Archivo | Qué es |
|---|---|
| [`notas/2026-10-09-retro-sprint-13.md`](notas/2026-10-09-retro-sprint-13.md) | Retro del Sprint 13 (vie 9/10), con acciones y responsables. |
| [`notas/2026-10-12-planning-sprint-14.md`](notas/2026-10-12-planning-sprint-14.md) | Planning del Sprint 14 (lun 12/10): qué se comprometió, cuántos puntos y qué quedó afuera. |
| [`notas/2026-10-15-1a1-con-mariana.md`](notas/2026-10-15-1a1-con-mariana.md) | 1:1 de Carla con su jefa (jue 15/10) sobre carga de trabajo y prioridades. |
| [`estado-semanal-anterior.md`](estado-semanal-anterior.md) | El reporte de estado que Carla mandó el lunes 12/10: semáforo, avance por épica, riesgos y próximos hitos. |
| [`../datos/sprints.csv`](../datos/sprints.csv) | Un registro por sprint: fechas, capacidad, puntos comprometidos y completados. |
| [`../datos/backlog.csv`](../datos/backlog.csv) | Las historias del backlog con épica, responsable, puntos, sprint y estado. |
| [`../datos/burndown-sprint-14.csv`](../datos/burndown-sprint-14.csv) | Puntos pendientes por día del Sprint 14. |

**Dashboard de puntos del proyecto** (subí `sprints.csv`, `backlog.csv` y `burndown-sprint-14.csv`):

```
Primero decime qué columnas tiene cada archivo y cuántas filas.
Después armame un dashboard interactivo (Artifact) del proyecto TurnoYa con:
- KPIs arriba: velocidad promedio de los últimos 3 sprints cerrados, % de cumplimiento
  (completado / comprometido) del último sprint cerrado y puntos pendientes del Sprint 14;
- velocidad por sprint (barras: comprometido vs. completado);
- burndown del Sprint 14 con la línea ideal, solo días hábiles;
- puntos por épica y por responsable (barras apiladas por estado);
- filtros por sprint, épica y responsable que actualicen todos los gráficos.
Abajo, una tabla con los totales que usaste, para que los compare con la planilla.
```

**El reporte de estado de esta semana** (subí `estado-semanal-anterior.md`, los tres CSV y las notas de [`notas/`](notas/)):

```
Este es el reporte de estado que mandé el lunes pasado. Armá el de esta semana (lunes 19/10)
con el mismo formato y las mismas secciones.
- Usá los CSV para los números (avance por épica, puntos del Sprint 14).
- Sumá lo que pasó esta semana según las notas: incidente del iPhone, licencia de Lucía,
  la fecha de la obra social.
- En cada sección, marcá qué cambió respecto del reporte anterior.
- Si un número del reporte anterior no coincide con los CSV, avisame en vez de corregirlo solo.
```

**Plan de capacidad del Sprint 15:**

```
Para el Sprint 15 (26/10 al 6/11) hay 34 puntos de candidatos y 26 de capacidad.
Con backlog.csv, la nota de refinamiento del 16/10 y lo que sabés de la licencia de Lucía,
proponeme dos alternativas de qué entra y qué queda afuera hasta llegar a 26 o menos.
Para cada alternativa: tabla de historias con puntos y responsable, carga por persona,
qué riesgo deja abierto (fechas con el cliente, bugs en producción) y a quién hay que avisarle.
Recomendame una y decime por qué. No cambies los puntos de ninguna historia.
```

**Tablero kanban de las tareas de las notas** (pegá las seis notas de [`notas/`](notas/)):

```
Sacá todas las tareas de estas seis notas y armame un tablero kanban interactivo (Artifact)
con columnas "Sin responsable", "Por hacer", "En curso" y "Hecho".
Cada tarjeta: tarea, responsable, fecha límite y de qué nota sale.
Marcá en rojo las que vencen esta semana y con un ícono las que contradicen otra nota.
Que se puedan arrastrar entre columnas y filtrar por persona.
```

**Acciones de retro que se repiten:**

```
Con la retro del Sprint 13 y el resto de las notas, buscá acciones que se repiten de retros
anteriores o que se acordaron y no se hicieron. Para cada una: desde cuándo está, quién la tenía,
si hay evidencia de que se hizo o de que volvió a fallar (en las notas o en la casilla),
y una propuesta para que esta vez se cumpla.
```

**Dónde se rompe con estos datos:**
- **Los totales.** Revisá que los puntos del dashboard coincidan con la suma de la planilla, por sprint y por épica. Si filtrás, los KPIs tienen que cambiar.
- **El burndown.** La línea ideal va solo por días hábiles: si baja en sábado y domingo, está mal hecha.
- **El reporte anterior no es la verdad.** Un reporte escrito a mano puede tener números que no coinciden con los datos. Que Claude te lo marque, no que lo "arregle" en silencio.

## Llevalo a tu trabajo

Elegí 5 mails reales de tu bandeja (sin datos sensibles o anonimizados) y repetí el **Paso 1**. Medí cuánto tardás con y sin Claude.
