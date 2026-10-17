# 07 · Revisar una lista y encontrar errores que se pasan por alto

**Tiempo:** 10 minutos · **Herramienta:** [claude.ai](https://claude.ai) · **Veredicto:** ✅ sirve: es de lo que mejor hace

## Un caso real

En la inscripción a esta misma charla, una persona escribió mal su mail. Un minuto después se volvió a anotar con el mail correcto. Revisando la lista con Claude apareció el duplicado y la letra cambiada, y así evitamos mandarle el link a una dirección que no existe. Es una tarea chica, pero a simple vista se pasa.

## El problema

La Clínica Sur mandó la lista de pacientes del piloto de TurnoYa para cargarla en el sistema. Antes de importarla, hay que encontrar los errores.

## Material

[`pacientes-piloto.csv`](pacientes-piloto.csv): 20 pacientes inventados, con errores escondidos a propósito.

## Paso a paso

**1.**

```
Te paso una lista de pacientes en CSV que vamos a importar a un sistema.
Antes de importarla, encontrá todos los problemas:
- personas duplicadas (aunque estén escritas distinto),
- mails mal escritos o imposibles,
- teléfonos incompletos o con otro formato,
- fechas inválidas,
- datos inconsistentes (por ejemplo, la misma provincia escrita de dos formas).

Dame una tabla: fila, problema, valor actual, corrección sugerida, y si estás seguro o es una sospecha.
[pegá el CSV]
```

**2.**

```
Devolveme el CSV corregido, sin duplicados. Sumá una columna "revisar" con "sí"
en las filas donde hiciste una corrección que no es segura.
```

## Qué deberías obtener

- **Duplicados:** Marta Gómez y "Marta Gomez" (filas 1 y 7). Jorge Fernández y "Jorge Fernandez" (filas 2 y 17), con otro formato de teléfono y "Bs. As.".
- **Mails:** `gmial.com`, `hotmial.com` y `gmail..com`.
- **Teléfonos:** uno vacío (Raúl Medina) y uno incompleto (`1145`).
- **Fecha imposible:** `2026-13-07`, porque no existe el mes 13.
- **A mirar:** pacientes de Córdoba y Mendoza con característica 11. Puede ser correcto: es una sospecha, no un error.

## Dónde se rompe

- **Corregir de más.** Si "arregla" un mail que podría ser real, se pierde el contacto. Las correcciones dudosas las confirma una persona (por eso la columna "revisar").
- **Listas largas.** Con miles de filas, pedile que revise por partes o que te dé reglas para aplicar en Excel.
- **Datos personales.** Una lista real de pacientes o clientes **no** se pega en una herramienta que tu organización no aprobó.

## Ir más lejos: con más datos

La lista de 20 se revisa a ojo. La de 300 ya no: ahí es donde una revisión ordenada ahorra horas y evita mandar recordatorios a mails que no existen.

| Archivo | Qué es |
|---|---|
| [`pacientes-piloto.csv`](pacientes-piloto.csv) | Los 20 pacientes del ejercicio base. |
| [`pacientes-piloto-completo.csv`](pacientes-piloto-completo.csv) | 300 filas: todas las altas del piloto de TurnoYa del 1/9 al 16/10/2026. Mismas columnas que la lista corta, más `sede` (Caballito, Flores, Almagro), `plataforma` (iOS, Android, Web) y `acepta_recordatorios` (si/no). **Todo es ficticio**: los mails tienen la forma nombre.apellido.NN@proveedor para que no coincidan con personas reales. Tiene errores escondidos a propósito. |

**1. El informe de calidad de datos:**

```
Te paso la lista completa de pacientes del piloto (300 filas, CSV) que vamos a importar a TurnoYa.
Revisala entera, fila por fila, y armá un informe de calidad de datos:
1. Una tabla resumen: tipo de problema, cantidad, y números de fila
   (fila 1 = el primer paciente, sin contar el encabezado).
   Tipos: duplicados (exactos y escritos distinto), mails, teléfonos, fechas
   (imposibles, futuras o anteriores al 1/9/2026, cuando arrancó la app),
   provincia escrita de varias formas, sede vacía, mayúsculas y minúsculas raras.
2. Una tabla de detalle: fila, columna, valor actual, problema, corrección sugerida,
   y "seguro" o "sospecha".
3. Cuántas filas tienen al menos un problema y qué porcentaje del total es.
No corrijas nada todavía.
[adjuntá pacientes-piloto-completo.csv]
```

**2. Lista corregida y lista "a confirmar":**

```
Ahora armá dos archivos:
- pacientes-corregidos.csv: todos los pacientes, una sola vez cada uno, con solo las
  correcciones obvias aplicadas (dominio de mail mal tipeado, provincia escrita de otra forma,
  mayúsculas). Sumá una columna "cambio" que diga qué tocaste en cada fila (vacía si nada).
- a-confirmar.csv: todo lo que no es obvio (teléfonos vacíos o incompletos, fechas imposibles,
  sedes vacías, cualquier sospecha). Esos datos quedan como estaban en el primer archivo.
  Columnas: nombre, apellido, dato a confirmar, valor actual, por qué.
Regla: si para corregir tenés que adivinar, no corrijas: va a "a confirmar".
Antes de terminar, decime cuántas filas tiene cada archivo, cuántos duplicados sacaste
y en cada duplicado qué fila conservaste y por qué. Verificá que
filas de pacientes-corregidos + duplicados sacados = 300.
```

**3. El dashboard de altas:**

```
Armame un dashboard interactivo (Artifact) con las altas del piloto de TurnoYa, a partir del CSV.
Quiero:
- KPIs arriba: total de filas, pacientes únicos (sin duplicados), % de filas con algún error,
  % que acepta recordatorios.
- Un gráfico de líneas con altas por día (1/9 al 16/10), con una marca en los fines de semana.
- Barras de altas por sede, apiladas por plataforma (iOS, Android, Web).
- Una barra o dona con el % de filas con error por tipo de error.
- Filtros por sede, plataforma y rango de fechas que actualicen todo.
Las filas con fecha imposible o futura no las ubiques en el gráfico por día:
mostralas aparte en un recuadro "fechas a revisar".
```

**4. El mail para confirmar datos:**

```
Escribí el mail que la mesa de ayuda de Clínica Sur le va a mandar a los pacientes
de la lista "a confirmar". Tiene que ser cálido, corto (menos de 100 palabras) y fácil
de responder para alguien de 75 años: decir quiénes somos, por qué escribimos,
qué dato necesitamos que confirme (dejá [dato] y [valor que tenemos]) y cómo responder.
Sin tecnicismos, sin "estimado usuario", sin urgencias falsas. Dame también una versión
de 2 líneas para mandar por SMS.
```

**5. Las reglas para la próxima vez:**

```
Con los errores que encontraste, armá 6 reglas de validación para el formulario de alta
de TurnoYa (por ejemplo: "el mail tiene una sola @ y un dominio con punto").
Para cada regla: qué controla, el mensaje que ve el paciente si se equivoca
(amable, en una línea) y cuál de los errores de esta lista habría evitado.
```

**Dónde se rompe (con estos datos):**

- **Listas largas, revisiones cortas.** Con 300 filas, Claude puede revisar con cuidado el principio y apurarse al final. Si el informe no menciona filas de octubre, pedile que revise por tramos de 100 y que te diga en qué fila terminó cada tramo.
- **Las fechas imposibles se "acomodan" solas.** En un dashboard, el navegador puede convertir un 31 de septiembre en 1 de octubre sin avisar. Si ves altas en meses donde el piloto no existía, o un día con una más de las que debería, ahí hay una fecha mal cargada.
- **Revisá que las cuentas cierren:** la suma de altas por sede tiene que dar el total de filas (o el de pacientes únicos, según lo que muestre), y los duplicados no se cuentan dos veces.

## Llevalo a tu trabajo

Tomá una lista que uses (proveedores, contactos, inventario) sin datos sensibles y pedile el paso 1.
