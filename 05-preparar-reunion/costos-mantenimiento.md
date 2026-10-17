<!-- Material ficticio para el taller "Cómo usar Claude en tu trabajo". Proveedores, precios y supuestos son inventados. -->

# TurnoYa · Costo de mantenimiento para 2027 (datos ficticios)

**Para:** Cdor. Gustavo Paz (Director financiero, Clínica Sur)
**Preparó:** Pedro Ruiz (Comercial) con Carla Méndez (PM), Nimbus Software · borrador del lunes 19/10/2026
**Período:** 12 meses de operación de TurnoYa en las 3 sedes del piloto (Caballito, Flores y Almagro).
**Moneda:** pesos argentinos, **IVA incluido** salvo donde se aclara.

---

## 1. Costos mensuales

| Concepto | Proveedor | Por mes | Por año | Estado |
|---|---|---:|---:|---|
| Hosting de servidores (producción, pruebas y respaldos) | NubeAR Hosting | $ 486.750 | $ 5.841.000 | Confirmado: factura de octubre 2026 (NUB-0042) |
| Abono de soporte (ver detalle en 3) | Nimbus Software | $ 650.000 | $ 7.800.000 | **A confirmar** |
| Servicio de envío de mails (recordatorios, hasta 50.000 mails por mes) | Proveedor externo | $ 58.000 | $ 696.000 | Confirmado: plan actual |
| Monitoreo de errores y registros técnicos | Proveedor externo | $ 42.000 | $ 504.000 | Confirmado: plan actual |
| **Subtotal mensual** | | **$ 1.236.750** | **$ 14.841.000** | |

## 2. Costos anuales y por horas

| Concepto | Detalle | Por año | Estado |
|---|---|---:|---|
| Cuenta de desarrollador de la tienda de apps de iOS | Renovación anual, se paga en dólares | $ 145.000 | Estimado (depende del tipo de cambio) |
| Dominio de la app | Renovación anual | $ 18.000 | Confirmado |
| Mantenimiento evolutivo | 60 horas por año × $ 34.000 por hora | $ 2.040.000 | Estimado |
| **Subtotal anual** | | **$ 2.203.000** | |

La tienda de apps de Android no tiene costo anual: el pago único ya se hizo en 2026.

## 3. Qué incluye cada cosa

**Abono de soporte ($ 650.000 por mes, a confirmar)**
- Nimbus atiende las consultas que la mesa de ayuda de Clínica Sur no puede resolver (segundo nivel), de lunes a viernes de 9 a 18.
- Corrección de errores de la app, hasta 16 horas por mes.
- Monitoreo de que la app esté funcionando y aviso de incidentes.
- **Qué falta confirmar:** Pedro todavía no cerró la cantidad de horas incluidas ni si el monto es con IVA incluido o más IVA. Si fuera más IVA, serían $ 786.500 por mes ($ 9.438.000 por año).

**Mantenimiento evolutivo (60 horas por año)**
- Adaptar la app a las versiones nuevas de iOS y Android (salen una vez por año cada una).
- Actualizar componentes por seguridad.
- No incluye funciones nuevas.

## 4. Total anual

| | Por año |
|---|---:|
| Costos mensuales × 12 (punto 1) | $ 14.841.000 |
| Costos anuales y por horas (punto 2) | $ 2.203.000 |
| **Total anual estimado** | **$ 17.044.000** |
| Equivalente mensual promedio | $ 1.420.333 |

**Verificación de la suma:**
- 486.750 + 650.000 + 58.000 + 42.000 = 1.236.750 por mes → × 12 = 14.841.000
- 60 × 34.000 = 2.040.000
- 145.000 + 18.000 + 2.040.000 = 2.203.000
- 14.841.000 + 2.203.000 = **17.044.000**
- 17.044.000 / 12 = 1.420.333,33

## 5. Supuestos

1. Precios de octubre 2026 **sin ajuste por inflación** durante los 12 meses. NubeAR ajusta el hosting cada tres meses según su contrato; el porcentaje del próximo ajuste no se conoce.
2. El volumen de uso se mantiene como en el piloto (3 sedes). Si la app se extiende a más sedes, el hosting y el envío de mails suben.
3. Tipo de cambio para la cuenta de la tienda de iOS: el del día del pago. El monto de la tabla es una estimación.
4. Valor hora para mantenimiento evolutivo: $ 34.000, promedio de las tarifas 2026 de Juan Paredes ($ 38.000) y Lucía Benítez ($ 30.000), que son quienes harían el trabajo. Se toma como precio final.
5. Las 60 horas de mantenimiento evolutivo surgen de la experiencia de Nimbus con otras apps parecidas. Pueden ser más si un cambio de sistema operativo rompe algo grande.

## 6. Qué NO está incluido

- Módulo de facturación a obras sociales: Pedro lo presupuesta aparte, después de la demo.
- Recordatorios por WhatsApp: fuera de alcance.
- Prueba de seguridad externa (prueba de intrusión), propuesta para diciembre de 2026: se presupuesta aparte.
- Lo que pueda cobrar la obra social Salud Plena por cada consulta de cobertura: **a confirmar** con Salud Plena.
- Costos internos de Clínica Sur (mesa de ayuda, recepción, área de sistemas).
