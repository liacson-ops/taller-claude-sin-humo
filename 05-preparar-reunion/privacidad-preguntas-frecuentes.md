<!-- Material ficticio para el taller "Cómo usar Claude en tu trabajo". La arquitectura, los proveedores y los procesos descriptos son inventados. No es asesoramiento legal. -->

# TurnoYa · Privacidad de los datos de pacientes: preguntas frecuentes (datos ficticios)

**Para:** Dra. Elena Ríos (Directora médica, Clínica Sur)
**Fuente:** respuestas de Juan Paredes (tech lead, Nimbus Software) a las preguntas de la Dra. Ríos, lunes 19/10/2026. Revisó: Carla Méndez.
**Estado:** borrador. Los puntos marcados **[A CONFIRMAR CON LEGAL]** todavía no tienen respuesta definitiva.

---

## 1. ¿Qué datos de los pacientes guarda la app?

| Dato | Para qué se usa |
|---|---|
| Nombre y apellido, DNI, fecha de nacimiento | Identificar al paciente y evitar turnos duplicados |
| Mail y teléfono celular | Ingresar a la app y recibir el recordatorio del turno |
| Obra social y número de afiliado | Validar la cobertura con Salud Plena |
| Turnos: fecha, hora, sede, especialidad y profesional | Agendar, confirmar y reprogramar |
| Comentario para el profesional (opcional, hasta 200 caracteres) | Que el paciente avise algo antes de la consulta |

**La app no guarda historia clínica, diagnósticos, recetas ni resultados de estudios.** No está conectada al sistema clínico de la clínica.

Ver el punto 8: el comentario es texto libre y un paciente podría escribir ahí información de salud.

## 2. ¿Dónde se guardan?

- En servidores de **NubeAR Hosting** (proveedor de infraestructura de Nimbus) en un centro de datos ubicado en la **Ciudad de Buenos Aires**.
- Se hace una **copia de respaldo diaria** en un segundo centro de datos del mismo proveedor, en **Córdoba**. Las copias se guardan 30 días y después se borran.
- Los datos de la app no se guardan en los celulares de los pacientes más allá de la sesión abierta.
- Excepción: ver el punto 9 sobre los mails de recordatorio.

## 3. ¿Están cifrados?

- **En tránsito:** toda la comunicación entre la app y los servidores viaja cifrada (HTTPS).
- **En reposo:** la base de datos y las copias de respaldo están cifradas.
- **Contraseñas:** no se guardan en texto legible. Nadie, ni siquiera Nimbus, puede ver la contraseña de un paciente.

## 4. ¿Quién puede ver los datos?

| Quién | Qué ve | Cómo |
|---|---|---|
| El paciente | Sus propios datos y turnos | App, con su usuario y contraseña |
| Recepción de cada sede | Turnos de **su** sede: nombre, DNI, teléfono, obra social | Panel web con usuario personal |
| Mesa de ayuda de Clínica Sur | Datos de contacto y turnos de las 3 sedes. No ve el comentario para el profesional | Panel web con usuario personal |
| Profesionales | Su propia agenda, con el comentario del paciente | Panel web con usuario personal |
| Nimbus Software | **Solo 2 personas** tienen acceso a producción: Juan Paredes y un segundo administrador de guardia. Con doble factor de autenticación | Cada acceso queda registrado en una bitácora que se guarda 12 meses |
| NubeAR Hosting | Administra los servidores, no accede al contenido de la base (está cifrada) | Según contrato con Nimbus |
| QA Externa (testing) | **No accede a producción.** Prueba en un entorno separado con datos ficticios | Decisión del kickoff de abril |

El resto del equipo de Nimbus (desarrollo, diseño, QA interno) trabaja con datos ficticios y no tiene acceso a producción.

## 5. ¿Cuánto tiempo se guardan?

- **Turnos:** 24 meses desde la fecha del turno. Después se anonimizan (se borran nombre, DNI y contacto) y quedan solo para estadísticas.
- **Cuenta del paciente:** mientras el paciente la use. Si pide la baja, se borra en 30 días (incluidas las copias de respaldo, que rotan cada 30 días).
- **Registros técnicos (logs):** 90 días.

## 6. ¿Cómo da su consentimiento el paciente?

- Al crear la cuenta, el paciente tiene que marcar una casilla (no viene marcada) aceptando los términos y la política de privacidad.
- La política explica qué datos se guardan, para qué, quién los ve y cómo pedir la baja.
- El texto de la política lo redactó Nimbus a partir de un modelo y lo revisó Ramiro. **No lo revisó el área de legales de Clínica Sur.** (Ver punto 10.)

## 7. ¿Qué dice la ley?

En Argentina rige la **Ley 25.326 de Protección de Datos Personales**. En términos generales:
- Los datos personales solo se pueden recolectar con consentimiento informado y para la finalidad que se le explicó a la persona.
- Los datos referidos a la salud se consideran **datos sensibles** y tienen una protección más estricta.
- Las personas tienen derecho a acceder a sus datos, a pedir que se corrijan y a pedir que se borren.
- Quien decide sobre la base de datos (en este caso, Clínica Sur) es el responsable. Quien la procesa por encargo (Nimbus, y a través de Nimbus, NubeAR) actúa como encargado y solo puede usarla para lo contratado.

Esto es un resumen general para orientar la conversación. **No reemplaza la opinión del área de legales de la clínica.**

## 8. El comentario libre: ¿es un dato de salud? **[A CONFIRMAR CON LEGAL]**

El campo "Comentario para el profesional" es texto libre. En el piloto, algunos pacientes escribieron cosas como "vengo por control de presión" o "traigo los análisis". Eso es información de salud.

Opciones que propone Nimbus, para que decida Clínica Sur con su área de legales:
1. Sacar el campo.
2. Dejarlo con un aviso: "No escribas información médica".
3. Dejarlo y tratarlo como dato sensible (más restricciones de acceso y de retención).

## 9. Los mails de recordatorio **[A CONFIRMAR CON LEGAL]**

Los recordatorios se mandan con un servicio externo de envío de mails. Ese servicio procesa nombre, mail, fecha, hora, sede y **especialidad** del turno, y sus servidores están **fuera de Argentina**.

Dos preguntas abiertas:
- Si eso cuenta como transferencia internacional de datos y qué condiciones contractuales hacen falta.
- Si conviene sacar la especialidad del mail (por ejemplo, "Tenés un turno mañana a las 10:00 en la sede Flores" en lugar de "Tenés un turno con Cardiología").

## 10. Contrato y registro de la base **[A CONFIRMAR CON LEGAL]**

- El 05/10 Nimbus mandó a Ramiro un borrador de contrato de encargado de tratamiento entre Clínica Sur y Nimbus. **Todavía no está firmado.**
- Falta definir quién inscribe la base de datos de TurnoYa ante el registro de la autoridad de control y a nombre de quién queda (se entiende que de Clínica Sur, como responsable).
- La revisión de la política de privacidad del punto 6 depende de esto mismo.

## 11. ¿Qué pasa si hay un problema de seguridad?

- Nimbus avisa a Clínica Sur **en menos de 24 horas** desde que detecta un incidente que afecte datos de pacientes.
- Contacto: Juan Paredes (tech lead), juan.paredes@nimbus-software.example, 11 5014-2207. Si no responde: Carla Méndez, 11 5014-2231.
- **El problema de iPhone del 17/10 no fue un incidente de seguridad:** el botón "Confirmar" no respondía en iOS 26. No hubo acceso indebido ni pérdida de datos.

## 12. ¿Se hizo alguna auditoría externa?

**No.** Todavía no se hizo una prueba de seguridad externa (prueba de intrusión). Nimbus propone hacerla en diciembre de 2026, con un proveedor especializado. No está incluida en el costo de mantenimiento: se presupuesta aparte.
