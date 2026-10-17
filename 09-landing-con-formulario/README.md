# 09 · Extra: una página de inscripción con formulario

**Tiempo:** 20 minutos · **Herramienta:** [claude.ai](https://claude.ai) con **Artifacts** · **Veredicto:** ✅ sirve para prototipos. Para producción, hace falta alguien que revise seguridad y datos.

## Cómo se usó en esta charla

La página de inscripción [lucasiacson.vercel.app](https://lucasiacson.vercel.app) se hizo con Claude:
- diseño "de diario",
- versión en español y portugués según de dónde entra la visita,
- tabla con el horario en cada país,
- formulario que guarda en una tabla,
- mail de confirmación automático con la invitación de calendario.

Debajo hay herramientas gratuitas o propias: Vercel para publicar y n8n para la tabla y los mails.

## Paso a paso (versión simple, solo con Claude)

**1. La página:**

```
Armame una página de inscripción de una sola pantalla para [tu evento o servicio].
Datos: [fecha, hora, lugar u online, precio].
Tiene que tener: título claro, para quién es, qué se van a llevar (3 puntos),
quién lo da, y un formulario con nombre, email y una pregunta.
Que se vea bien en el celular. Usá [colores o el manual del ejercicio 08].
```

**2. La confianza:**

```
¿Qué le falta a esta página para que alguien que no me conoce confíe y se anote?
Proponé 3 cambios concretos y aplicalos.
```

**3. El texto legal mínimo:**

```
Agregá un apartado corto de "Tus datos" que diga para qué se usan, que no se ceden a terceros
y cómo pedir que los borren.
```

## Para ir más lejos (con ayuda técnica)

- **Publicar:** Vercel o Netlify en su plan gratuito.
- **Guardar las inscripciones:** un webhook de n8n, Google Forms o una planilla.
- **Mail automático:** n8n con una cuenta de correo propia.

## Dónde se rompe

- **El formulario del artifact no guarda nada** por sí solo: es una maqueta. Para recibir inscripciones hay que conectarlo a algo.
- **Seguridad.** Nunca pegues claves (API keys, contraseñas) dentro de la página: quedan visibles para cualquiera.
- **Datos personales.** Si guardás mails, decí para qué los usás y cumplí con lo que dijiste.

## Ir más lejos: con más datos

Con el contenido real, las sedes y un lote de preinscripciones de ejemplo, el ejercicio pasa de "una página linda" a una maqueta que se puede mostrar al cliente, más el tablero para seguir cómo viene la campaña.

| Archivo | Qué es |
|---|---|
| [`contenido-landing.md`](contenido-landing.md) | Borrador del área comercial para la landing de TurnoYa (ficticio): título, beneficios, cómo funciona en 3 pasos, 8 preguntas frecuentes, aviso de privacidad breve y campos del formulario. Es un borrador: tiene cosas para revisar. |
| [`sedes.csv`](sedes.csv) | Las 5 sedes de Clínica Sur (ficticias): sede, dirección, horario, especialidades y teléfono. TurnoYa funciona hoy solo en Caballito, Flores y Almagro. |
| [`preinscripciones-ejemplo.csv`](preinscripciones-ejemplo.csv) | 180 preinscripciones **de ejemplo, inventadas**, del 1 al 16/10/2026: fecha, sede, rango de edad, plataforma, cobertura, cómo se enteró y si acepta recordatorios. No tiene nombres ni mails a propósito. |

**1. La landing con formulario de preinscripción:**

```
Armame la landing de preinscripción a TurnoYa (Artifact) con el contenido que te paso.
Una sola página, pensada primero para el celular, con letra base de 18 px y botones grandes.
Secciones: encabezado con el botón, beneficios, cómo funciona en 3 pasos, el formulario,
preguntas frecuentes (en acordeón) y el aviso de privacidad.
El formulario: los campos sugeridos, con validación amable (mensaje en una línea debajo
del campo, no en una ventana), las dos casillas sin marcar de entrada, y el mensaje
de "Listo" al enviar. Si te sirve, usá la identidad del ejercicio 08.
Antes de armarla, decime si hay algo en el contenido que no deberíamos publicar tal cual.
[adjuntá contenido-landing.md]
```

**2. El selector de sede desde el CSV:**

```
Sumale a la landing un selector de sede armado con sedes.csv: una tarjeta por sede con
dirección, horario, especialidades y teléfono (que se pueda tocar para llamar).
Caballito, Flores y Almagro se pueden elegir; Boedo y Villa Crespo aparecen como
"Próximamente: dejá tus datos y te avisamos". Al elegir una sede, que el campo "Sede"
del formulario se complete solo. Agregá un buscador por especialidad que filtre las tarjetas.
[adjuntá sedes.csv]
```

**3. El dashboard de inscripciones:**

```
Armame un dashboard interactivo (Artifact) con las preinscripciones de ejemplo.
Quiero:
- KPIs arriba: total de preinscripciones, % en sedes del piloto vs. sedes "próximamente",
  % que acepta recordatorios y % de 60 años o más.
- Un gráfico de líneas con preinscripciones por día, con una marca el 8/10
  (ese día se pusieron los carteles QR en las salas de espera).
- Barras por sede, apiladas por "cómo se enteró".
- Una tabla cruzada de rango de edad por plataforma preferida, resaltando "Necesito ayuda".
- Filtros por sede, cobertura y rango de edad que actualicen todo.
Al final, 3 conclusiones en una línea cada una, y la cantidad exacta de filas que leíste.
[adjuntá preinscripciones-ejemplo.csv]
```

**4. Revisar lo que la página promete:**

```
Revisá la landing contra lo que TurnoYa hace hoy: pedir turno, confirmarlo, cancelarlo
y recibir recordatorios por mail. Reprogramar tiene un error y se está arreglando;
los recordatorios por WhatsApp no están en el proyecto; la obra social Salud Plena
se integra en noviembre. Marcá cada frase que promete algo que la app no hace,
y proponé el reemplazo. Después revisá el aviso de privacidad: ¿dice para qué se usan
los datos, quién los recibe, cuánto tiempo se guardan y cómo pedir que los borren?
Señalá lo que falta o contradice al resto de la página. Podés citar la Ley 25.326,
pero no le inventes artículos: si no estás seguro, decí "consultar con un abogado".
```

**5. La prueba con una persona mayor:**

```
Hacé de cuenta que sos una paciente de 78 años que entra a la landing desde el celular,
con la letra agrandada. Recorrela de arriba a abajo y contame, paso por paso, dónde dudarías,
qué palabra no entenderías y en qué parte del formulario abandonarías. Después aplicá
los 3 cambios que más ayuden.
```

**Dónde se rompe (con estos datos):**

- **El Artifact no guarda datos reales por sí solo.** El formulario es una maqueta: al tocar "Preinscribirme" no queda nada en ningún lado. Para recibir inscripciones de verdad hace falta conectarlo a una base de datos o una planilla, y eso lo tiene que revisar alguien que sepa de seguridad. Un Artifact no reemplaza una base de datos.
- **Una casilla no es consentimiento.** El consentimiento lo da un texto claro que dice para qué se usan los datos y que se cumple después. Si el aviso de privacidad promete algo que nadie controla, la casilla no sirve. Y las preinscripciones reales de pacientes no se pegan en una herramienta que tu organización no aprobó: usá los datos de ejemplo.
- **Revisá que el dashboard lea todas las filas.** El total tiene que dar 180 y la suma por sede también. Si cambiás sedes.csv, la landing no se actualiza sola: el CSV quedó copiado dentro del Artifact.
