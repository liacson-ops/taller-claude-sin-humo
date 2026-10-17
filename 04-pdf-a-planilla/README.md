# 04 · Pasar facturas en PDF a una planilla (y encontrar el error)

**Tiempo:** 15 minutos · **Herramienta:** [claude.ai](https://claude.ai) (subí PDFs con el clip 📎) · **Veredicto:** ✅ sirve, pero **los números se controlan siempre**

## El problema

Tres facturas de proveedores del proyecto llegaron por mail. Hay que cargarlas en la planilla de gastos. Una de ellas tiene un error que, si no se ve, se paga de menos y vuelve como reclamo.

## Material

En [`facturas/`](facturas/) (todas ficticias):
- `factura-NUB-0042.pdf`: hosting, factura B.
- `factura-QAE-1187.pdf`: pruebas de carga, factura A.
- `factura-COW-0315.pdf`: alquiler de sala, factura A.

## Paso a paso

**1.** Subí los 3 PDFs a Claude con el clip 📎 y pedí:

```
Pasá estas 3 facturas a una tabla con estas columnas:
proveedor, CUIT, tipo y número de factura, fecha de emisión, vencimiento,
subtotal, IVA, total, concepto.
Usá exactamente los números que figuran. Si un dato no está, dejá la celda vacía.
```

**2.** El control que nadie hace:

```
Ahora controlá cada factura:
- ¿subtotal + IVA da el total?
- ¿cantidad × precio da cada importe?
- ¿la fecha de vencimiento es posterior a la de emisión?
Mostrame la cuenta que hiciste y marcá con ❗ cualquier inconsistencia.
```

**3.** Para llevar a tu planilla:

```
Dame la tabla en formato CSV con punto y coma como separador, para pegar en Excel o Google Sheets.
```

**4.** La respuesta al proveedor:

```
Escribí un mail breve y amable al proveedor que tiene el error, pidiendo que la corrija.
```

## Qué deberías obtener

- **QA Externa (0001-00001187):** subtotal $1.090.000 + IVA $228.900 = **$1.318.900**, pero el total impreso dice **$1.274.000**. ❗
- **Coworking Palermo (0002-00000315):** emitida el 05/10 con **vencimiento 28/09**, anterior a la emisión. ❗
- **NubeAR:** sin errores. Es factura B: el IVA no se discrimina.

## Dónde se rompe

- **La IA "corrige" sin avisar.** Puede escribir el total que *debería* ser en vez del que *figura*. Por eso el paso 2 pide mostrar la cuenta.
- **Formatos de número.** "1.274.000,00" (formato argentino) se puede leer mal. Revisá que la planilla no muestre 1,274.
- **PDF escaneados o fotos.** Funcionan peor. Si el PDF es una imagen, revisá cada número a mano.

## Ir más lejos: con más datos

Seis meses de facturas de los mismos tres proveedores y las órdenes de compra que las aprobaron. Alcanza para armar la planilla de gastos del proyecto, auditarla y compararla con el presupuesto. Todo es ficticio.

| Archivo | Qué es |
|---|---|
| [`facturas-historicas/`](facturas-historicas/) | 13 facturas PDF de abril a septiembre de 2026: NubeAR Hosting (hosting mensual, factura B), QA Externa (testing tercerizado, factura A) y Coworking Palermo (sala de reuniones, factura A). Algunas tienen errores. |
| [`ordenes-de-compra.csv`](ordenes-de-compra.csv) | Las 15 órdenes de compra del período (abril a octubre): orden, proveedor, concepto, mes del servicio, monto aprobado **con IVA incluido** y quién lo aprobó. Datos ficticios. |
| [`../datos/presupuesto.csv`](../datos/presupuesto.csv) | Presupuesto contra real del proyecto por mes y rubro (abril a octubre de 2026). Datos ficticios. |

Subí las 16 facturas (las 13 históricas más las 3 de [`facturas/`](facturas/)). Si tu cuenta no te deja subir tantos archivos juntos, hacelo en dos tandas y pedile que siga la misma tabla.

**1. Todas las facturas en una planilla**

```
Te paso 16 facturas de proveedores de un proyecto. Pasalas a UNA tabla con estas columnas:
archivo, proveedor, CUIT, tipo (A o B), número, fecha de emisión, vencimiento,
mes del servicio (según la descripción), concepto, cantidad, precio unitario,
subtotal, IVA, total impreso, monto en letras.
Una fila por factura. Usá exactamente lo que figura impreso, aunque esté mal.
En las facturas B el IVA no se discrimina: dejá subtotal e IVA vacíos.
Ordená por fecha de emisión. Al final, dame la suma de "total impreso" por proveedor.
```

**2. Auditar las cuentas**

```
Ahora auditá cada factura de la tabla. Para cada una, controlá:
- cantidad × precio unitario = importe de cada línea
- suma de importes = subtotal
- IVA = 21 % del subtotal (en las A)
- subtotal + IVA = total
- el monto en letras dice lo mismo que el número
- el vencimiento es posterior a la emisión
- el mes del servicio es coherente con la fecha de emisión
- no hay dos facturas por el mismo concepto y el mismo mes
Mostrame la cuenta que hiciste en cada control. Armá una tabla final solo con las facturas
que tienen algún problema: número, qué control falla, valor impreso, valor correcto
y diferencia en pesos.
```

**3. Cruzar contra lo aprobado**

```
Te paso ordenes-de-compra.csv. El monto aprobado es con IVA incluido.
Cruzá cada factura con su orden de compra (mismo proveedor y mismo mes de servicio) y decime:
- facturas que superan lo aprobado (cuánto y en qué porcentaje)
- facturas que no tienen orden de compra
- órdenes de compra que no tienen factura
- órdenes que tienen más de una factura
Usá el total CORRECTO de cada factura (el que resulta de la auditoría), no el impreso,
y aclaralo en la tabla.
```

**4. Dashboard de gastos y presupuesto contra real**

```
Armame un dashboard interactivo (Artifact) con los gastos de proveedores del proyecto,
usando la tabla de facturas auditada y ../datos/presupuesto.csv.
- Arriba, 4 KPIs: total facturado impreso, total correcto, diferencia por errores
  y monto pagado de más si se pagara todo lo impreso.
- Gráfico de barras apiladas: gasto por mes (abril a octubre) y por proveedor.
- Gráfico de líneas: presupuesto contra real por mes para los rubros Hosting, QA externa
  y Coworking del CSV, y al lado lo que dicen las facturas para esos mismos meses.
- Tabla de desvíos: mes, rubro, presupuesto, real, diferencia y % de desvío,
  con los desvíos mayores a 10 % resaltados.
- Filtros por proveedor y por mes, y un interruptor para ver totales impresos o corregidos.
- Una nota al pie que diga qué criterio de mes usaste (emisión o servicio).
Los números tienen que salir de los datos, no los inventes.
```

**5. Un mail por cada error**

```
Para cada factura con problemas (auditoría y cruce con órdenes de compra), escribí un mail
breve y amable al proveedor. Cada mail tiene que decir: número de factura, qué está mal,
cuál es el valor correcto según nuestra cuenta y qué le pedimos (nota de crédito,
factura corregida o anulación). Firmá como Administración de Nimbus Software.
Si un proveedor tiene más de un problema, juntalos en un solo mail.
```

**6. Para tu planilla**

```
Dame la tabla de facturas auditada como CSV con punto y coma como separador, montos sin
separador de miles y con coma decimal, y una columna "estado" con OK, ERROR o REVISAR.
```

**Dónde se rompe con más datos**

- **Muchos PDFs, más errores de lectura.** Con 16 archivos es más fácil que lea mal un número o mezcle dos facturas. Antes de auditar, compará al azar 3 filas de la tabla contra el PDF.
- **El control que pasa no siempre está bien.** Si solo pedís "subtotal + IVA = total", una factura con el IVA mal calculado puede pasar el control. Pedí cada cuenta por separado.
- **Mes de emisión o mes de servicio.** El dashboard cambia según cuál uses. Revisá que el total del dashboard coincida con la suma de la tabla y que el criterio sea el mismo que en ../datos/presupuesto.csv.

## Llevalo a tu trabajo

Tomá 3 facturas o comprobantes reales que no tengan datos sensibles (o tapalos) y repetí los pasos 1 y 2.
