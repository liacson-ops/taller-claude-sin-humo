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

## Llevalo a tu trabajo

Tomá 3 facturas o comprobantes reales que no tengan datos sensibles (o tapalos) y repetí los pasos 1 y 2.
