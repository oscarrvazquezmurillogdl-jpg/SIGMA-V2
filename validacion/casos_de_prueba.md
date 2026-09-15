# Casos de prueba iniciales

Los casos se definen sin importes para evitar presentar datos inventados como evidencia. Antes de ejecutarlos deben completarse con valores sintéticos identificados como tales.

| Caso | Cambio controlado | Comportamiento esperado | Condición de rechazo |
|---|---|---|---|
| Base | Ninguno | La identidad de caja se cumple en todos los periodos | Diferencia aritmética no explicada |
| Retraso de cobranza | Desplazar una entrada a una fecha posterior | El efectivo no aumenta antes de la nueva fecha | Reconocer la entrada en la fecha original |
| Pago obligatorio | Incorporar una salida no diferible | Caja y buffer disminuyen por el mismo importe | Signo contrario o doble contabilización |
| Crédito no utilizable | Marcar una línea como no disponible | No se incorpora al efectivo ni al buffer | Tratar crédito aprobado como disponible |
| Dato faltante | Eliminar un campo obligatorio | La ejecución se detiene o queda rechazada | Sustituir el vacío por cero |
| Cambio de moneda | Introducir moneda distinta sin regla | La ejecución se detiene | Sumar importes sin conversión documentada |
| Ajuste conciliado | Registrar un ajuste con evidencia | Se preserva la continuidad con explicación | Ajustar sin trazabilidad |
| Escenario adverso | Aplicar una perturbación autorizada | El escenario se separa del caso base | Mezclar resultados o sobrescribir datos observados |

## Prueba de no anticipación

Una validación histórica solo puede utilizar datos disponibles hasta la fecha de corte seleccionada. Si utiliza información posterior, el backtesting queda rechazado por fuga temporal.

## Pendientes

- Importes sintéticos aprobados.
- Tolerancia monetaria.
- Frecuencia temporal.
- Horizonte.
- Umbrales de eventos.
- Métricas de error y aceptación.
