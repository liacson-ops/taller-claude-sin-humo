# 08 · Extra: armar opciones de identidad visual

**Tiempo:** 15 minutos · **Herramienta:** [claude.ai](https://claude.ai) con **Artifacts** (vista previa de páginas) · **Veredicto:** 🟡 a mirar: genial para explorar, la decisión final es tuya

## Cómo se usó en esta charla

La identidad "El diario sin humo" (papel, tinta, naranja, tipografía de diario) salió de pedirle a Claude **5 caminos distintos** con un mismo set de piezas (portada de carrusel, story, flyer), compararlos lado a lado y elegir. Después se probaron 7 colores de acento antes de quedarnos con uno. Mirá el resultado en [lucasiacson.vercel.app](https://lucasiacson.vercel.app).

## Paso a paso

**1. El brief.** Completalo con tu proyecto (o usá el de TurnoYa):

```
Necesito una identidad visual para [qué es: un emprendimiento, un proyecto, una marca personal].
Para quién: [público].
Qué tiene que transmitir: [3 palabras].
Qué NO quiero: [por ejemplo, el violeta con degradé típico de las marcas de IA].

Armame una página HTML con 5 caminos visuales distintos. Para cada uno:
concepto en una línea, paleta (con códigos), tipografías gratuitas de Google Fonts,
un logo simple, y 3 piezas de ejemplo: una portada de carrusel de Instagram,
una story y un flyer. Al final, una tabla comparativa.
```

**2. Iterá sobre el que te gusta:**

```
Me gusta la opción [N]. Mostrame 5 variantes de color de acento manteniendo todo lo demás,
y verificá que el texto se lea bien sobre cada color (contraste).
```

**3. El manual:**

```
Armá el manual de marca de la opción elegida: colores con usos, tipografías,
reglas de tono de voz (así sí / así no) y ejemplos de aplicación.
```

## Dónde se rompe

- **"Inspirado en" ≠ copiar.** No le pidas que imite la marca de otra empresa.
- **Contraste.** Lo que se ve bien en tu pantalla puede no leerse en un celular al sol. Pedile que lo verifique.
- **Tipografías.** Que sean gratuitas (Google Fonts), salvo que tengas licencia.

## Ir más lejos: con más datos

Con un brief completo, Claude deja de proponer "algo lindo" y empieza a proponer algo que cumple requisitos. Y con los textos reales de la app, el diseño se prueba con contenido de verdad, no con "Lorem ipsum".

| Archivo | Qué es |
|---|---|
| [`brief-de-marca.md`](brief-de-marca.md) | El brief de TurnoYa (ficticio): qué es, público (pacientes de 25 a 80 años y recepcionistas), tono, valores, qué evitar, competencia inventada y las restricciones de accesibilidad que no se negocian. |
| [`textos-de-la-app.md`](textos-de-la-app.md) | Los textos actuales de 14 pantallas de la app, tal cual están hoy, más frases que se escuchan en la mesa de ayuda. Varios son confusos a propósito. |

**1. Tres direcciones de identidad:**

```
Te paso el brief de marca de TurnoYa. Armame una página (Artifact) con 3 direcciones
de identidad bien distintas entre sí. Para cada una:
- concepto en una línea y a qué parte del brief responde,
- paleta de 5 colores con códigos y el contraste de cada color de texto sobre su fondo,
- tipografía de Google Fonts (que distinga 1/l/I y 0/O),
- logo e ícono de la app,
- aplicadas a 3 piezas con textos reales: la pantalla de inicio, la pantalla "Elegí el horario"
  y el cartel A4 con QR para la sala de espera.
Al final, una tabla que compare las 3 contra cada punto de "Qué evitar" y de
"Restricciones de accesibilidad" del brief (cumple / no cumple / a revisar).
[adjuntá brief-de-marca.md]
```

**2. La revisión de accesibilidad, como tablero:**

```
Armame un dashboard interactivo (Artifact) para revisar la accesibilidad de las 3 direcciones.
Quiero:
- KPIs arriba: cantidad de combinaciones texto/fondo, cuántas pasan AA (4,5:1 texto normal,
  3:1 texto grande) y el contraste más bajo de cada dirección.
- Una matriz de todas las combinaciones de colores de cada paleta, con el valor de contraste
  y "pasa / no pasa" con texto e ícono (no solo color).
- Un selector de dirección y un deslizador de tamaño de letra (16 a 32 px) que muestre
  una tarjeta de turno de ejemplo con ese tamaño.
- Un botón que simule cómo se ve cada paleta con daltonismo rojo-verde.
- Una lista de "a corregir" con la combinación que falla y un color alternativo que sí pase.
```

**3. Textos de la app para personas mayores:**

```
Te paso los textos actuales de TurnoYa y el brief de marca. Reescribilos pensando en una
paciente de 78 años que usa el celular con la letra agrandada y, si duda, prefiere llamar.
Dame una tabla por pantalla: texto actual, texto nuevo, qué problema resolvés.
Reglas: frases de menos de 12 palabras, una sola acción por botón, nada de palabras en inglés
ni siglas, los errores dicen qué hacer después, y "Cancelar" no puede significar dos cosas.
Usá las frases de la mesa de ayuda para saber qué confunde.
Al final, una lista de las 5 palabras que sacaste y por cuál las reemplazaste.
[adjuntá textos-de-la-app.md y brief-de-marca.md]
```

**4. El prototipo con los textos nuevos:**

```
Con la dirección [N] y los textos nuevos, armame un prototipo clickeable (Artifact) del flujo
"pedir un turno": inicio → especialidad y sede → horario → confirmar → turno reservado.
Que se pueda navegar de punta a punta, con un botón para pasar a letra grande (200 %)
y otro para modo oscuro. Avisame en qué pantalla el diseño se rompe con letra grande.
```

**5. Usted o vos:**

```
El brief deja abierto si la app trata de "vos" o de "usted". Escribí la pantalla de confirmación
y el mail de recordatorio en las dos versiones, y dame 3 argumentos a favor de cada una
pensando en este público. No decidas vos: armame la comparación para que la decida la clínica.
```

**Dónde se rompe (con estos datos):**

- **El contraste "calculado a ojo".** Si Claude dice "pasa AA" sin mostrar el número, pedile el valor. Y confirmalo vos con un verificador de contraste gratuito: no te quedes con la palabra del modelo.
- **Textos más cortos no siempre son más claros.** "Turno OK" es corto y no le dice nada a quien duda. Leé los textos nuevos en voz alta, o mejor, mostráselos a alguien de 70 años.
- **Lo que no está en el brief, lo inventa.** Si le pedís un ícono "de salud" sin restricciones, puede volver al celeste de hospital que el brief pide evitar. Pegá siempre el brief completo, no un resumen.

## Llevalo a tu trabajo

¿Tenés una presentación o un documento que siempre se ve distinto? Pedile un mini manual con 3 colores, 2 tipografías y 5 reglas.
