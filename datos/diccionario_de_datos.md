# Diccionario de datos inicial

Los campos siguientes son una propuesta de estructura. Su obligatoriedad y granularidad deben aprobarse antes de implementar el motor.

| Campo | Tipo previsto | Significado | Evidencia esperada | Estado |
|---|---|---|---|---|
| fecha | fecha | Periodo al que corresponde el registro | Calendario y documento fuente | Requerido |
| caja_inicial | moneda | Efectivo disponible al inicio | Conciliación bancaria y caja | Requerido |
| entradas_confirmadas | moneda | Cobros con sustento y fecha | Facturas, cobranza, banco | Requerido |
| entradas_no_confirmadas | moneda | Entradas sujetas a condición | Evidencia y regla de escenario | Opcional, no sumar al caso base sin autorización |
| salidas_obligatorias | moneda | Pagos no diferibles | Nómina, impuestos, deuda, contratos | Requerido |
| salidas_diferibles | moneda | Pagos cuya fecha puede modificarse | Autorización y condición contractual | Condicionado |
| financiamiento_utilizable | moneda | Recursos realmente disponibles | Contrato, saldo y restricciones | Condicionado |
| obligaciones_proximas | moneda | Compromisos dentro de la ventana definida | Calendario de pagos | Requiere definir ventana |
| caja_minima_operativa | moneda | Reserva necesaria para sostener operación | Método aprobado | Pendiente de definición |
| moneda | texto | Moneda de denominación | Documento fuente | Requerido |
| fuente_documental | texto | Origen verificable del dato | Referencia o identificador | Requerido |
| estado_evidencia | categoría | Observado, conciliado, estimado, supuesto o faltante | Revisión | Requerido |
| escenario | texto | Caso base o escenario autorizado | Documento de escenario | Requerido |
| observaciones | texto | Limitación o explicación | Responsable | Opcional |

## Reglas

- Un campo vacío no equivale a cero.
- No deben sumarse monedas diferentes sin una regla de conversión documentada.
- Los importes deben conservar signo y naturaleza.
- Todo ajuste manual debe incluir responsable, fecha, motivo y evidencia.
- Los datos reales identificables no deben subirse a este repositorio público.
