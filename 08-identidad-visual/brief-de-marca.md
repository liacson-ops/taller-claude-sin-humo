# Brief de marca: TurnoYa

> Material ficticio para el taller. Nimbus Software, Clínica Sur, TurnoYa y la competencia que se nombra acá son inventados. Cualquier parecido con empresas o apps reales es casualidad.

**Quién lo pide:** Carla Méndez (PM, Nimbus Software) con Martín Ferro (UX/UI).
**Para quién:** Clínica Sur, cliente de Nimbus. Contacto: Ramiro Ibáñez (Gerente de Operaciones).
**Fecha:** octubre de 2026.

## Qué es TurnoYa

Una app para pedir, confirmar y cancelar turnos médicos de Clínica Sur desde el celular (iOS y Android) o desde la web. Del otro lado, las recepcionistas usan un panel web para ver los turnos del día.

Está en piloto desde el 1 de septiembre de 2026 en tres sedes: Caballito (sede central, Av. Rivadavia 4500), Flores y Almagro. En septiembre se pidieron 1.240 turnos por la app y las llamadas a recepción bajaron un 31 % en esos consultorios (septiembre contra agosto).

Hoy la app usa los colores por defecto del sistema y un logo provisorio. Antes de abrirla a todas las sedes, la clínica quiere una identidad propia.

## Público

**Pacientes de 25 a 80 años.** No es un público "tecnológico": es el público de una clínica de barrio.

| Grupo | Cómo es | Qué necesita de la app |
|---|---|---|
| 25 a 44 años | Usa el celular para todo, pide turnos en el colectivo o de noche. | Rapidez: pedir un turno en menos de un minuto. |
| 45 a 64 años | Muchas veces saca turnos para sus padres o sus hijos. | Claridad sobre para quién es el turno, cobertura y sede. |
| 65 a 80 años | Usa el celular, pero con letra agrandada. Desconfía de lo que no entiende y prefiere llamar si duda. | Letra grande, pocos pasos, palabras conocidas y la certeza de que el turno quedó hecho. |

**Recepcionistas de las tres sedes.** Usan el panel 8 horas por día, en un mostrador con gente esperando y el teléfono sonando. Necesitan ver de un vistazo quién llegó, quién falta y qué turno se canceló.

## Qué tiene que transmitir

Tres palabras: **confiable, simple, cercana.**

- **Confiable:** es salud. La persona tiene que sentir que el turno es real y que sus datos están cuidados.
- **Simple:** cada pantalla, una sola decisión.
- **Cercana:** habla como la recepcionista amable de siempre, no como un banco ni como una startup.

## Tono de voz

- Trato de **vos**, como el resto de la comunicación de Clínica Sur. (Tema abierto: algunos pacientes mayores prefieren "usted". La clínica pidió que se lo planteemos.)
- Frases cortas, en positivo y con la acción primero: "Elegí el día", no "A continuación deberá seleccionar una fecha".
- Palabras de todos los días: "turno", "sede", "obra social". Nada de "slot", "booking", "sede efectora" ni "credenciales".
- Cuando algo falla, la culpa nunca es del paciente, y siempre se dice qué hacer después.

## Valores

1. **Nadie se queda afuera.** Si una persona de 80 años no puede usarla, la app no está terminada.
2. **Claridad antes que estilo.** Si un adorno compite con un botón, se va el adorno.
3. **Privacidad a la vista.** La Dra. Elena Ríos (Directora médica) pidió que se note que los datos de salud se cuidan.
4. **El tiempo del otro vale.** Del paciente y de la recepcionista.

## Qué evitar

- El violeta con degradé y los brillos típicos de las marcas "de IA" o de tecnología.
- El rojo como color principal: en una clínica se lee como urgencia o error.
- El celeste y blanco "de hospital" genérico, que hace que todas las apps de salud se vean iguales.
- Tipografías finas, condensadas o en mayúsculas sostenidas.
- Íconos sin texto (un ícono de "engranaje" solo no dice nada a muchos pacientes).
- Fotos de banco de imágenes con médicos sonriendo a cámara.
- Emojis en la interfaz.
- Palabras en inglés y siglas sin explicar.

## Competencia (ficticia)

| App (ficticia) | Cómo se ve | Qué aprendemos |
|---|---|---|
| **AgendaSalud 360** | Azul hospitalario, formularios largos, mucha información por pantalla. | Se ve seria, pero los pacientes mayores abandonan a mitad del formulario. |
| **Turnalia** | Verde lima y negro, ilustraciones juveniles, muchos emojis. | Se recuerda, pero no se lee al sol y no transmite confianza a mayores de 60. |
| **MiTurnoNet** | La app de una prepaga: publicidad de planes dentro de la app. | Mezclar venta con salud genera desconfianza. TurnoYa no muestra publicidad. |

## Restricciones de accesibilidad (no negociables)

- **Contraste mínimo AA** de las pautas WCAG 2.1: 4,5:1 para texto normal y 3:1 para texto grande (desde 24 px, o 19 px en negrita) y para bordes de botones y campos.
- **Letra grande:** texto base de 18 px en la app y 16 px como mínimo absoluto en cualquier lugar. Tiene que seguir funcionando si el paciente agranda la letra del celular al 200 %.
- **Botones grandes:** área táctil mínima de 48 × 48 px y separación entre botones para no tocar el de al lado.
- **Nunca solo color:** el estado de un turno (confirmado, cancelado, a confirmar) se indica con color + texto + ícono.
- **Números claros:** la tipografía tiene que distinguir bien 1, l e I, y 0 y O (horarios, números de turno, teléfonos).
- **Nada de texto sobre fotos.**
- **Movimiento mínimo:** sin animaciones que distraigan, y respetando la opción "reducir movimiento" del celular.
- **Lectores de pantalla:** todo botón e ícono con una etiqueta que se pueda leer en voz alta.

## Restricciones prácticas

- Tipografías gratuitas de Google Fonts.
- Tiene que convivir con el logo de Clínica Sur (azul marino sobre blanco) en la pantalla de inicio: "TurnoYa · Clínica Sur".
- Ícono de la app reconocible en 48 px.
- Funciona en modo claro y modo oscuro.
- **Plazo:** la demo al directorio de la clínica es el jueves 22/10. La identidad nueva **no** se usa en esa demo: es para la versión que sale a todas las sedes.

## Piezas que hay que diseñar

1. Logo e ícono de la app.
2. Pantalla de inicio y pantalla "Elegí el horario".
3. Botón principal, botón secundario y mensaje de error.
4. Cartel A4 con código QR para la sala de espera.
5. Mail de recordatorio de turno.
6. Panel de recepción (vista del día).
