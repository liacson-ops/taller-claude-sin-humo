<!-- Documento ficticio para un taller. Nimbus Software, Clínica Sur, TurnoYa y todas las cifras son inventadas. -->

# TurnoYa · Reporte de estado semanal

**Semana:** lunes 12/10/2026 · **Enviado por:** Carla Méndez (PM) · **Para:** Mariana Quiroga (gerenta de Delivery), Pedro Ruiz · **CC:** Juan Paredes

## Semáforo

| Frente | Estado | Comentario |
|---|---|---|
| **General** | Amarillo | Avanzamos bien, pero la integración con la obra social depende de un tercero. |
| Alcance | Verde | Sin cambios de alcance desde el último reporte. |
| Plazos | Amarillo | Credenciales de prueba de Salud Plena todavía sin fecha. |
| Calidad | Amarillo | 10 bugs abiertos al cierre del Sprint 13 (3 en el Sprint 12). |
| Presupuesto | Verde | Dentro de lo previsto. |

## Sprint 13 (28/9 al 9/10) · cerrado

- Comprometido: 31 pts · Completado: **30 pts (97 %)**.
- Velocidad promedio de los últimos 3 sprints: **27 pts**.
- Lo más importante: historial de turnos pasados, confirmación en un toque desde el mail, preparación para iOS 26.

## Sprint 14 (12/10 al 23/10) · arrancó hoy

- Comprometido: **33 pts** con capacidad de 28. El objetivo es la demo al directorio del jueves 22/10 y la integración con Salud Plena.
- Si las credenciales no llegan esta semana, la integración real (13 pts) queda en riesgo.

## Avance por épica (puntos hechos / puntos del backlog)

| Épica | Hechos | Total | Avance |
|---|---|---|---|
| Turnos | 94 | 154 | 61 % |
| Calidad | 52 | 81 | 64 % |
| Infraestructura | 52 | 87 | 60 % |
| Login y marca | 32 | 54 | 59 % |
| Confirmación | 35 | 60 | 58 % |
| Recordatorios | 23 | 48 | 48 % |
| Obra social | 11 | 52 | 40 % |
| Reprogramación | 17 | 62 | 27 % |
| Facturación | 0 | 12 | 0 % |
| **Total** | **316** | **610** | **52 %** |

## Piloto (septiembre, 3 sedes)

- 1.240 turnos pedidos por la app (iOS, Android y web).
- 31 % menos llamadas a recepción en los consultorios del piloto (septiembre contra agosto).

## Riesgos

| # | Riesgo | Impacto | Qué hacemos | Responsable |
|---|---|---|---|---|
| 1 | Las credenciales de prueba de Salud Plena no llegan a tiempo | Alto: la integración es una entrega del contrato (30/10) | Ramiro las gestiona con la obra social | Carla |
| 2 | Sprint 14 comprometido por encima de la capacidad (33 contra 28) | Medio | Seguimiento diario en el burndown | Carla |
| 3 | Staging se cae por el certificado SSL | Medio: perdimos medio día dos veces | Renovación automática | Juan |
| 4 | 10 bugs abiertos, dos en producción (reprogramar y recordatorios) | Medio | Se priorizan en el Sprint 15 | Sofía |

## Próximos hitos

| Fecha | Hito |
|---|---|
| mié 21/10 | Ensayo de la demo |
| jue 22/10 11:00 | Demo al directorio de Clínica Sur: pedir turno, confirmar, reprogramar y recordatorios |
| vie 23/10 | Cierre del Sprint 14 y retro |
| lun 26/10 | Inicio del Sprint 15 |
| jue 30/10 | Entrega contractual: integración con Salud Plena funcionando en producción |

## Necesito de ustedes

- Pedro: que los pedidos nuevos de Ramiro pasen por mí antes de responder.
- Mariana: OK para incorporar un segundo QA en 2027 (lo armo con números).
