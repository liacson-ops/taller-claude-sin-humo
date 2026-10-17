<!-- Material ficticio para el taller "Cómo usar Claude en tu trabajo". Personas, empresas y datos son inventados. -->

# Minuta · Kickoff de TurnoYa con el directorio de Clínica Sur (datos ficticios)

**Fecha:** jueves 09/04/2026, 10:00 a 11:30
**Lugar:** sala de directorio, Clínica Sur (Av. Rivadavia 4500, Caballito)
**Redactó:** Carla Méndez · enviada a los presentes el 10/04/2026

**Presentes**
- Clínica Sur: Ramiro Ibáñez (Gerente de Operaciones), Dra. Elena Ríos (Directora médica), Cdor. Gustavo Paz (Director financiero).
- Nimbus Software: Carla Méndez (PM), Juan Paredes (tech lead), Pedro Ruiz (Comercial).

---

## 1. Objetivo del proyecto

Ramiro presentó el problema: la recepción de las sedes recibe la mayoría de los pedidos de turno por teléfono y en horas pico no da abasto. TurnoYa es una app (iOS, Android y web) para que los pacientes pidan, confirmen y reprogramen turnos solos.

Se acordó arrancar con un **piloto en tres sedes: Caballito, Flores y Almagro**, desde el **1 de septiembre de 2026**, y presentar los resultados al directorio en octubre.

## 2. Alcance acordado para el piloto

- Pedir turno, confirmar turno, reprogramar turno y recordatorio por mail el día anterior.
- Solo consultas ambulatorias. Estudios y cirugías quedan afuera.
- Integración con la obra social Salud Plena para validar la cobertura del paciente al pedir el turno.
- **Fuera de alcance:** recordatorios por WhatsApp (los pidió Ramiro). Pedro explicó que requiere aprobación del proveedor de mensajería para el número de la clínica. Se evalúa para una fase 2.
- **Fuera de alcance:** facturación a obras sociales.

## 3. Metas del piloto

| Meta | Cómo se mide | Quién mide |
|---|---|---|
| Al menos 1.000 turnos por mes pedidos por la app en las sedes del piloto | Registros de la app, mes de septiembre | Nimbus |
| Bajar al menos 25 % las llamadas a recepción en las sedes del piloto | Central telefónica, septiembre contra agosto | Clínica Sur (Ramiro) |
| Medir la satisfacción de los pacientes | Encuesta corta al terminar el turno (NPS) | Clínica Sur con apoyo de Nimbus |

## 4. Comentarios del directorio

- **Dra. Ríos:** "Un turno no es un dato clínico, pero que alguien se atiende con un oncólogo dice mucho". Pidió un resumen escrito de dónde se guardan los datos, quién accede y cómo se protegen, **antes de que arranque el piloto**. También pidió que en las pruebas nunca se usen datos reales de pacientes. Preguntó a quién llamar si algo sale mal.
- **Cdor. Paz:** preguntó cuánto cuesta mantener la app por año después del piloto. Carla respondió que todavía no hay número cerrado y que se estima antes de la presentación de resultados. Paz: "Decime un número, aunque sea un rango, pero decime de dónde sale". Preguntó si el hosting estaba atado al dólar (Juan: se factura en pesos, con ajuste trimestral).
- **Ramiro:** "Si la recepción no lo nota, para mí no existe".

## 5. Decisiones

1. Piloto en Caballito, Flores y Almagro desde el 01/09/2026.
2. Recordatorios solo por mail en esta etapa.
3. Los entornos de prueba usan siempre datos ficticios. Ninguna persona externa a Nimbus (incluida la empresa de testing) accede a datos reales.
4. Presentación de resultados del piloto al directorio en octubre de 2026 (fecha a definir por Ramiro).

## 6. Compromisos

| # | Compromiso | Responsable | Fecha comprometida |
|---|---|---|---|
| 1 | Piloto funcionando en las 3 sedes, en iOS, Android y web | Nimbus (Carla) | 01/09/2026 |
| 2 | Integración real con Salud Plena funcionando (fecha de contrato) | Nimbus (Juan) | 30/10/2026 |
| 3 | Resumen escrito de seguridad y privacidad para la Dra. Ríos | Nimbus (Juan) | Antes del inicio del piloto (31/08/2026) |
| 4 | Estimación del costo anual de mantenimiento (hosting, soporte, licencias) | Nimbus (Pedro y Carla) | Antes de la presentación de resultados |
| 5 | Logos de Clínica Sur en alta resolución para la pantalla de ingreso | Clínica Sur (Ramiro) | 30/04/2026 |
| 6 | Medición de llamadas a recepción de agosto y septiembre | Clínica Sur (Ramiro) | 05/10/2026 |
| 7 | Encuesta de satisfacción a pacientes del piloto | Clínica Sur (Ramiro) con diseño de Nimbus (Martín Ferro) | Durante septiembre |
| 8 | Reporte mensual de avance a Ramiro | Nimbus (Carla) | Primer lunes de cada mes |

**Próxima reunión con el directorio:** presentación de resultados del piloto, octubre de 2026.
