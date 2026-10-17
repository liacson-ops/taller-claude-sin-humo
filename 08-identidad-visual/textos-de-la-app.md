# Textos actuales de la app TurnoYa

> Material ficticio para el taller. Son los textos que hoy tiene la app del piloto, copiados tal cual pantalla por pantalla. Varios están escritos "desde el sistema" y no desde el paciente: la idea es mejorarlos. Lo que está entre llaves `{así}` lo completa la app.

## 1. Bienvenida

- Título: **Bienvenido/a a TurnoYa**
- Texto: Gestioná tus turnos de forma ágil y eficiente.
- Botones: **Ingresar** · **Registrarse** · **Continuar como invitado**

## 2. Registro

- Título: **Crear cuenta**
- Campo: Ingresá tu N° de afiliado o DNI
- Campo: Contraseña (mín. 8 caracteres, 1 mayúscula, 1 número y 1 carácter especial)
- Casilla: Acepto los TyC y la Política de Privacidad
- Botón: **Registrarse**
- Error: Error 401: credenciales inválidas.

## 3. Inicio

- Saludo: Hola, {nombre}
- Tarjeta: Próximo turno: {dd/mm} {hh:mm} · {especialidad} · {sede}
- Botones: **+ Nuevo turno** · **Mis turnos** · **Más**

## 4. Pedir turno: especialidad y sede

- Título: **Nuevo turno**
- Campo: Seleccioná especialidad
- Campo: Profesional: Indistinto
- Campo: Seleccioná sede efectora
- Campo: Cobertura: seleccioná plan/OS
- Botón: **Buscar disponibilidad**

## 5. Elegir horario

- Título: **Disponibilidad**
- Texto: Seleccioná un slot disponible.
- Sin resultados: No hay disponibilidad para los parámetros seleccionados. Modificá los filtros.

## 6. Confirmar el turno

- Pregunta: ¿Confirmás la reserva del slot {hh:mm}?
- Botones: **Confirmar** · **Cancelar**

## 7. Turno reservado

- Texto: Reserva generada OK. ID #{codigo}. Recordá presentarte 15' antes con orden médica si corresponde.
- Botón: **Volver al inicio**

## 8. Mis turnos

- Título: **Mis turnos**
- Estados posibles: Pendiente · Confirmado · Reprogramado · Ausente · Anulado
- Botones en cada turno: **Reprogramar** · **Anular**

## 9. Aviso para confirmar asistencia (notificación)

- Texto: Tenés un turno pendiente de confirmación. Si no confirmás dentro de las 24 h, el turno será liberado automáticamente.

## 10. Reprogramar

- Texto: Reprogramar implica la anulación del turno vigente y la generación de uno nuevo sujeto a disponibilidad.
- Botones: **Aceptar** · **Volver**

## 11. Anular

- Pregunta: ¿Desea anular el turno? Esta acción no se puede deshacer.
- Botones: **Sí** · **No**

## 12. Errores

- Error general: Ocurrió un error inesperado. Intente nuevamente más tarde. (cód. 500)
- Sin conexión: Network error
- Sesión vencida: Su sesión ha expirado. Vuelva a loguearse.

## 13. Mail de recordatorio

- Asunto: Recordatorio turno #{codigo}
- Cuerpo: Le recordamos que posee un turno asignado para el día {dd/mm/aaaa} a las {hh:mm} hs en {sede}. En caso de no poder concurrir, solicitamos anularlo con 24 hs de anticipación a través de la app. Este es un mensaje automático, por favor no responder.

## 14. Panel de recepción

- Título: **Agenda del día**
- Estados: En sala · Atendido · No show · Sobreturno
- Botón: **Dar presente**

## Lo que se escucha en la mesa de ayuda

Frases de pacientes que llamaron durante el piloto (inventadas, pero del tipo que llega):

- "Toqué *Cancelar* para volver atrás y no sé si me borró el turno."
- "¿Qué es 'sede efectora'? Yo me atiendo en Flores."
- "Me dice que tengo un turno *pendiente*. ¿Pendiente de qué? ¿Lo tengo o no lo tengo?"
- "La contraseña no me la acepta y no me dice qué le falta."
- "Me llegó un mail que dice que no responda. ¿Entonces a quién le pregunto?"
- "¿Qué es un slot?"
