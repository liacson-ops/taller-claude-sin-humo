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
