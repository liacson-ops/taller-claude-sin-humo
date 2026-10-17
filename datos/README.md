# Datos del proyecto TurnoYa

**Para:** los pedidos de nivel 2 de cada ejercicio (dashboards, reportes, cálculos) · **Herramienta:** [claude.ai](https://claude.ai) (plan gratuito)

> **Todo es ficticio.** Nimbus Software, Clínica Sur, la obra social Salud Plena, las personas, los pacientes, los montos y los comentarios son inventados para este taller. Cualquier parecido con empresas o personas reales es casualidad.

## El contexto en 5 líneas

1. **Nimbus Software** desarrolla **TurnoYa**, una app de turnos médicos (iOS, Android y web) para la **Clínica Sur**.
2. El equipo trabaja en sprints de 2 semanas desde el 13/04/2026. Hoy es **lunes 19/10/2026, 8:40**: el Sprint 14 está en curso y el 15 se planifica el jueves.
3. El piloto en 3 sedes (Caballito, Flores y Almagro) arrancó el **1/9**: en septiembre se pidieron 1.240 turnos por la app y bajaron las llamadas a recepción.
4. Desde el **sábado 17/10** los pacientes con iPhone no pueden confirmar turnos. El arreglo sale hoy a las 18.
5. El **jueves 22/10** hay demo con el directorio de la clínica, y el Sprint 15 tiene más trabajo (34 puntos) que capacidad (26).

## Archivos

| Archivo | Qué es | Filas |
|---|---|---|
| [`equipo.csv`](equipo.csv) | Las 6 personas de Nimbus: rol, dedicación, tarifa y licencias. | 6 |
| [`sprints.csv`](sprints.csv) | Los 15 sprints: capacidad, puntos comprometidos y completados, bugs abiertos. | 15 |
| [`backlog.csv`](backlog.csv) | Todas las historias, tareas y bugs con **puntos de historia**, estado y responsable. | 181 |
| [`burndown-sprint-14.csv`](burndown-sprint-14.csv) | Puntos que faltan por día en el Sprint 14, ideal y real. | 10 |
| [`horas.csv`](horas.csv) | Horas cargadas por persona y tarea en los sprints 13 y 14. | 320 |
| [`bugs.csv`](bugs.csv) | Los bugs registrados desde mayo, con severidad y plataforma. | 69 |
| [`piloto-turnos.csv`](piloto-turnos.csv) | Turnos por día, sede y canal, del 1/8 al 18/10. | 1.185 |
| [`mesa-de-ayuda.csv`](mesa-de-ayuda.csv) | Consultas de pacientes a la mesa de ayuda de la clínica, del 1/9 al 19/10. | 155 |
| [`presupuesto.csv`](presupuesto.csv) | Presupuesto contra gasto real por mes y rubro, de abril a octubre. | 42 |
| [`riesgos.csv`](riesgos.csv) | Registro de riesgos con probabilidad, impacto y mitigación. | 14 |
| [`encuesta-pacientes.csv`](encuesta-pacientes.csv) | Encuesta dentro de la app: NPS, facilidad de uso y comentarios. | 150 |

Todos son CSV con coma como separador, en UTF-8, con fechas `AAAA-MM-DD` y montos en pesos argentinos sin separador de miles (IVA incluido).

## Diccionario de datos

### `equipo.csv`

| Columna | Qué significa |
|---|---|
| `persona` | Nombre y apellido. |
| `rol` | Rol en el proyecto. |
| `empresa` | Siempre Nimbus Software. |
| `dedicacion_pct` | Porcentaje de su tiempo dedicado a TurnoYa. |
| `tarifa_hora_ars` | Costo por hora que se usa para costear el proyecto, en pesos. |
| `horas_semanales` | Horas por semana dedicadas al proyecto (40 × dedicación). |
| `licencias` | Vacaciones o licencias en 2026, como texto con fechas. |

### `sprints.csv`

| Columna | Qué significa |
|---|---|
| `sprint` | Número de sprint (1 a 15). |
| `inicio`, `fin` | Lunes de inicio y viernes de cierre. |
| `objetivo` | Objetivo del sprint. |
| `capacidad_puntos` | Puntos que el equipo estimó que podía hacer (descuenta feriados y licencias). |
| `puntos_comprometidos` | Puntos que se tomaron en la planificación. |
| `puntos_completados` | Puntos terminados (velocidad). En el Sprint 14 es parcial, al 19/10. En el 15 está vacío. |
| `puntos_agregados_en_curso` | Puntos que entraron con el sprint ya empezado. |
| `puntos_quitados_en_curso` | Puntos que salieron con el sprint ya empezado. |
| `bugs_abiertos_al_cierre` | Bugs sin resolver el último día del sprint (en el 14, al 19/10). |
| `estado` | Cerrado, En curso o Planificado. |
| `nota` | Feriados, licencias y cambios de alcance. |

### `backlog.csv`

| Columna | Qué significa |
|---|---|
| `id` | Identificador (TY-101 en adelante). |
| `titulo` | Qué hay que hacer. |
| `tipo` | Historia, Tarea, Bug o Spike (investigación). |
| `epica` | Turnos, Confirmación, Reprogramación, Recordatorios, Obra social, Login y marca, Facturación, Infraestructura o Calidad. |
| `puntos` | Puntos de historia: 1, 2, 3, 5, 8 o 13. |
| `estado` | Hecho, En revisión, En curso, Por hacer, Bloqueado o Fuera de alcance. |
| `responsable` | Quién lo tiene asignado (vacío si nadie). |
| `sprint` | Sprint donde está (vacío si todavía no se planificó). |
| `prioridad` | Alta, Media o Baja. |
| `creado`, `cerrado` | Fecha de alta y fecha en que pasó a Hecho. |
| `etiquetas` | Etiquetas separadas por punto y coma (por ejemplo `demo;privacidad`). |

### `burndown-sprint-14.csv`

| Columna | Qué significa |
|---|---|
| `dia` | Día hábil del sprint (1 a 10). |
| `fecha` | Fecha de ese día hábil (12/10 al 23/10). |
| `puntos_restantes_ideal` | Línea ideal: de 33 puntos a 0 en 10 días, al cierre de cada día. |
| `puntos_restantes_real` | Puntos que faltaban al cierre del día. Vacío desde el 20/10 (todavía no pasó). |
| `puntos_completados_dia` | Puntos terminados ese día. |
| `puntos_agregados`, `puntos_quitados` | Cambios de alcance de ese día. |
| `nota` | Qué pasó. |

### `horas.csv`

| Columna | Qué significa |
|---|---|
| `fecha` | Día trabajado (del 28/09 al 18/10). |
| `persona` | Quién cargó las horas. |
| `sprint` | Sprint al que corresponde la fecha. |
| `tarea_id` | Ítem del backlog. Vacío en gestión, reuniones o tareas comerciales. |
| `horas` | Horas cargadas (en decimales: 1.5 = una hora y media). |
| `facturable` | `si` o `no` (las guardias del incidente y lo comercial no se facturan). |
| `comentario` | Detalle corto. |

### `bugs.csv`

| Columna | Qué significa |
|---|---|
| `id` | Identificador (BUG-001 en adelante). |
| `titulo` | Qué falla. |
| `severidad` | Crítica, Alta, Media o Baja. |
| `plataforma` | iOS, Android, Web o Backend. |
| `detectado`, `resuelto` | Fechas (resuelto vacío si sigue abierto). |
| `estado` | Abierto, En curso, Resuelto, Descartado o Duplicado. |
| `sprint` | Sprint en que se trabajó o se va a trabajar (vacío si no está planificado). |
| `reportado_por` | QA, Cliente, Paciente o Equipo. |
| `backlog_id` | Ítem del backlog relacionado (la historia donde apareció o el bug cargado como ítem). |

### `piloto-turnos.csv`

Una fila por día, sede y canal.

| Columna | Qué significa |
|---|---|
| `fecha` | Día (del 01/08 al 18/10/2026). |
| `sede` | Caballito, Flores o Almagro. |
| `canal` | App iOS, App Android, Web, Teléfono o Presencial. Antes del 1/9 los tres primeros están en 0 porque la app no existía. |
| `turnos_pedidos` | Turnos pedidos ese día por ese canal. |
| `confirmados`, `cancelados`, `ausentes` | Qué pasó con esos turnos: cuántos se confirmaron, se cancelaron o el paciente no fue. |
| `llamadas_recepcion` | Llamadas que recibió la recepción de esa sede ese día, por cualquier motivo. **Solo está en las filas de canal Teléfono**; en el resto queda vacía para no contarla dos veces. |

Flores no abre los sábados. Los domingos no hay atención: solo entran algunos turnos por la app.

### `mesa-de-ayuda.csv`

| Columna | Qué significa |
|---|---|
| `ticket` | Número de consulta (MA-0001 en adelante). |
| `fecha_hora` | Fecha y hora (`AAAA-MM-DD HH:MM`). Llega hasta el 19/10 a las 8:40. |
| `sede` | Sede del paciente. |
| `canal` | Teléfono, Mail o Mostrador. |
| `plataforma` | iOS, Android, Web o "Sin app". |
| `categoria` | Pedir turno, Confirmar turno, Cancelar turno, Reprogramar, Recordatorios, Obra social, Acceso / contraseña o Consulta general. |
| `descripcion` | Lo que dijo el paciente, resumido por la mesa de ayuda. |
| `estado` | Resuelto, Pendiente o Derivado a Nimbus. |
| `minutos_resolucion` | Minutos hasta resolverla (vacío si no está resuelta). |

### `presupuesto.csv`

| Columna | Qué significa |
|---|---|
| `mes` | Mes (`AAAA-MM`), de 2026-04 a 2026-10. |
| `rubro` | Desarrollo, QA externa, Hosting, Coworking, Licencias o Soporte. |
| `presupuestado_ars` | Lo que se presupuestó para ese mes. |
| `real_ars` | Lo que se registró como gasto ese mes (facturas recibidas en el mes; desarrollo = horas × tarifa). Vacío si todavía no hay dato. |
| `observacion` | Aclaraciones: facturas de octubre, meses parciales, montos a confirmar. |

### `riesgos.csv`

| Columna | Qué significa |
|---|---|
| `id` | R-01 en adelante. |
| `riesgo` | Qué puede pasar (o qué ya pasó). |
| `probabilidad`, `impacto` | De 1 (bajo) a 5 (alto). |
| `responsable` | Quién lo sigue. |
| `mitigacion` | Qué se hace para bajarlo. |
| `estado` | Abierto, En seguimiento o Materializado (ya pasó). |
| `fecha_revision` | Próxima revisión. |

### `encuesta-pacientes.csv`

| Columna | Qué significa |
|---|---|
| `respuesta` | R-001 en adelante. |
| `fecha` | Día de la respuesta. |
| `sede`, `plataforma` | Sede del paciente y desde dónde usa la app. |
| `edad_rango` | 18-29, 30-44, 45-59, 60-74 o 75 o más. |
| `nps` | "¿Qué tan probable es que recomiendes TurnoYa?" de 0 a 10. NPS = % de 9 y 10 menos % de 0 a 6. |
| `facilidad` | "¿Qué tan fácil te resultó?" de 1 a 5. |
| `comentario` | Comentario libre (puede estar vacío). |

## Cómo subir los archivos a claude.ai

1. Bajá el repo (**Code → Download ZIP**) y descomprimilo.
2. En [claude.ai](https://claude.ai), abrí un chat nuevo y tocá el **clip** (o arrastrá los archivos al cuadro de texto).
3. Subí **solo los archivos que pide cada pedido**: 2 o 3 por vez alcanzan.
4. Pegá el pedido y enviá. Si pedís un dashboard, Claude lo arma como **Artifact** en el panel de la derecha.

> **Plan gratuito:** alcanza, pero tiene límites de tamaño por archivo y de mensajes por período. Si te dice que el archivo es muy grande o te quedás sin mensajes, subí menos archivos por vez, abrí un chat nuevo o esperá a que se renueve el límite. `piloto-turnos.csv` es el más grande: subilo como archivo, no lo pegues en el chat.

**La consigna de siempre:** antes de cualquier gráfico, pedile que te diga **qué columnas encontró y cuántas filas tiene cada archivo**. Y después del gráfico, que te muestre **los totales que usó** para que los compares con la planilla.

## Pedidos para armar dashboards

**1. Dashboard de puntos** (subí `backlog.csv`, `sprints.csv` y `burndown-sprint-14.csv`):

```
Te subo backlog.csv, sprints.csv y burndown-sprint-14.csv del proyecto TurnoYa.
Primero decime qué columnas encontraste y cuántas filas tiene cada archivo.

Después armame un dashboard interactivo (Artifact) de puntos de historia con:
- KPIs arriba: velocidad promedio de los sprints cerrados, velocidad de los últimos 3,
  % de cumplimiento (completado / comprometido) y puntos que faltan en el Sprint 14;
- barras de comprometido vs. completado por sprint, con la capacidad como línea;
- el burndown del Sprint 14: línea ideal y línea real, marcando los días
  en que se agregaron o quitaron puntos;
- puntos terminados (estado Hecho) por épica y por responsable;
- filtros por sprint y por épica que actualicen todos los gráficos.
No incluyas el Sprint 14 (en curso) ni el 15 (planificado) en los promedios.
Abajo, una tabla con los totales que usaste por sprint, para comparar con la planilla.
```

**2. Capacidad del Sprint 15** (subí `backlog.csv`, `sprints.csv`, `equipo.csv` y `riesgos.csv`):

```
El Sprint 15 tiene ítems candidatos por 34 puntos y la capacidad es de 26.
Con backlog.csv (filtrá sprint = 15), sprints.csv, equipo.csv y riesgos.csv:
1. Listá los candidatos con puntos, responsable, prioridad y etiquetas. Sumalos.
2. Compará la capacidad de 26 con la velocidad real de los últimos 3 sprints cerrados.
3. Proponé qué sacar para llegar a 26 o menos, y por qué. Tené en cuenta:
   compromisos del contrato, bugs que afectan a producción, dependencias externas,
   licencias del equipo y quién tiene más carga.
4. Dame dos alternativas en una tabla: qué entra, qué sale, total de puntos y el riesgo
   de cada opción.
No inventes fechas ni compromisos que no estén en los archivos: si falta un dato, decilo.
```

**3. Dashboard del piloto** (subí `piloto-turnos.csv`):

```
Te subo piloto-turnos.csv: turnos por día, sede y canal del piloto de TurnoYa.
Primero decime qué columnas encontraste, cuántas filas hay y el rango de fechas.

Armame un dashboard interactivo (Artifact) con:
- KPIs: turnos pedidos por la app (iOS + Android + Web) en septiembre,
  llamadas a recepción de agosto y de septiembre, y el % de variación;
- turnos por día apilados por canal, con filtro por sede y por rango de fechas;
- adopción de la app: % de turnos pedidos por la app sobre el total, por semana;
- llamadas a recepción por día y por sede, antes y después del 1/9;
- el impacto del incidente de iPhone: confirmados por día de App iOS desde el 1/10,
  comparados con App Android, marcando el sábado 17/10.
Ojo: llamadas_recepcion está solo en las filas de canal Teléfono.
Abajo, una tabla con los totales por mes y por canal que usaste.
```

**4. Presupuesto vs. real** (subí `presupuesto.csv`):

```
Te subo presupuesto.csv del proyecto TurnoYa (montos en pesos, IVA incluido).
Primero decime qué columnas hay y qué celdas están vacías.

Armame un dashboard interactivo (Artifact) con:
- presupuestado vs. real por mes (barras) y el acumulado de abril a octubre (línea);
- una tabla por rubro y mes con el desvío en pesos y en %, en rojo si supera el 10 %;
- los 3 desvíos más grandes, con una explicación de una línea usando la columna observacion;
- un filtro por rubro.
Las celdas vacías no son cero: mostralas como "sin dato" y no las uses en los desvíos.
Si un mes está incompleto, aclaralo en el gráfico.
Al final: con los montos de octubre, estimá el costo mensual de mantener TurnoYa
(hosting, soporte y licencias) y el costo anual, y decime qué supuestos usaste.
```

**5. Mesa de ayuda y encuesta** (subí `mesa-de-ayuda.csv` y `encuesta-pacientes.csv`):

```
Te subo mesa-de-ayuda.csv y encuesta-pacientes.csv.
Primero decime qué columnas tiene cada uno y cuántas filas.

Armame un dashboard interactivo (Artifact) con:
- consultas por día y por categoría (apiladas), con filtro por plataforma y por sede;
- tiempo promedio de resolución por canal;
- NPS por plataforma y por rango de edad (NPS = % de 9 y 10 menos % de 0 a 6),
  con la cantidad de respuestas al lado de cada valor;
- NPS de iOS antes y después del 17/10;
- los comentarios de la encuesta agrupados en temas: cuántos hay de cada tema
  y 2 ejemplos textuales con su número de respuesta.
No reescribas ni inventes comentarios: citá textual.
Abajo, la tabla de totales que usaste.
```

**6. Matriz de riesgos** (subí `riesgos.csv`):

```
Te subo riesgos.csv. Armame un Artifact con una matriz de riesgos de 5 x 5
(probabilidad en un eje, impacto en el otro), con cada riesgo como un punto
con su id, color según el estado y el detalle al pasar el mouse.
Al lado, una tabla ordenada por probabilidad x impacto, con filtros por estado
y por responsable.
Después decime cuáles necesitan una decisión antes de la demo del jueves 22/10
y quién la tiene que tomar. Si un riesgo no tiene mitigación concreta, marcalo.
```

## Dónde se rompe

- **Totales que no cuadran.** Un dashboard prolijo no garantiza que las sumas estén bien. Compará siempre los totales que te muestra con una suma propia en la planilla (Excel o Google Sheets). Si no coinciden, pedile que te muestre las filas que usó.
- **Datos que faltan.** Hay celdas vacías a propósito (meses sin cerrar, montos a confirmar, días del sprint que todavía no pasaron). Claude puede completarlas "para que el gráfico quede lindo". Pedile que marque lo que falta como "sin dato" y que no lo estime salvo que vos lo pidas.
- **Gráficos que suman mal.** Columnas que solo valen para algunas filas, sprints en curso mezclados con cerrados, meses parciales comparados con meses completos. Revisá qué filas entraron en cada número.
- **Datos con errores, como cualquier planilla real.** Antes de graficar, pedile: "revisá si hay valores raros, duplicados, fechas imposibles o celdas vacías donde no debería haberlas, y listalos". Lo que encuentre, lo confirmás vos contra la planilla.
