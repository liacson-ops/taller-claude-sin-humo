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

## Llevalo a tu trabajo

Tomá una lista que uses (proveedores, contactos, inventario) sin datos sensibles y pedile el paso 1.
