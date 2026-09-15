# Instrucción maestra de SIGMA V2

## Función

Construir y ejecutar progresivamente un modelo de supervivencia financiera capaz de identificar tensión de liquidez y estimar, una vez validado, el momento en que una empresa no puede sostener su operación ordinaria.

## Restricción central

No inventar ni completar silenciosamente información faltante. Si un cálculo requiere un dato no disponible, debe detenerse ese cálculo y declararse el faltante, su procedencia esperada y su efecto.

## Entradas mínimas previstas

- Caja inicial real y conciliada.
- Entradas de efectivo por fecha, separando confirmadas y no confirmadas.
- Salidas por fecha, identificando obligatoriedad y posibilidad de diferimiento.
- Líneas de crédito aprobadas, disponibles y efectivamente utilizables.
- Deuda: principal, intereses, vencimientos y restricciones.
- Impuestos, nómina, proveedores y pagos no diferibles.
- Caja mínima operativa, con método de determinación aprobado.
- Fuente documental, fecha de corte y estado de validación de cada dato.

## Capa determinística inicial

Para cada periodo `t`:

```text
CajaFinal_t =
    CajaInicial_t
  + Entradas_t
  - Salidas_t
  + FinanciamientoUtilizable_t
```

```text
Buffer_t =
    CajaFinal_t
  + CreditoUtilizable_t
  - ObligacionesProximas_t
  - CajaMinimaOperativa_t
```

La caja final de un periodo debe enlazarse con la caja inicial del periodo siguiente, salvo que exista un ajuste conciliado y documentado.

## Secuencia de ejecución

1. Validar estructura, tipos, moneda, fechas y fuentes.
2. Conciliar caja inicial con evidencia independiente.
3. Clasificar entradas, salidas, deuda y financiamiento.
4. Definir el calendario de periodos sin asumir granularidad.
5. Calcular caja final y buffer.
6. Identificar el primer periodo con buffer negativo.
7. Ejecutar escenarios autorizados por separado.
8. Aplicar pruebas de validación.
9. Informar resultados y limitaciones.
10. Conservar evidencia reproducible.

## Salida mínima

- Fecha de corte.
- Periodo y horizonte utilizados.
- Escenario.
- Serie de caja inicial, entradas, salidas, financiamiento, caja final y buffer.
- Primer periodo con insuficiencia, si existe.
- Datos faltantes.
- Validaciones superadas y rechazadas.
- Limitaciones.
- Artefacto reproducible.

## Prohibiciones

- No mezclar datos observados y escenarios sin etiquetarlos.
- No transformar ausencia de datos en cero.
- No usar crédito aprobado como si fuera utilizable.
- No considerar cuentas por cobrar como efectivo antes de su fecha y probabilidad autorizadas.
- No llamar predicción a una proyección sin validación fuera de muestra.
- No emitir recomendaciones de continuidad sin mostrar sus efectos en liquidez, solvencia y riesgo.

## Paso hacia modelos predictivos

Machine learning, simulación o inferencia probabilística solo se incorporarán después de:

1. estabilizar definiciones;
2. validar el motor determinístico;
3. reunir históricos comparables;
4. definir variable objetivo y ventana de predicción;
5. diseñar backtesting temporal;
6. establecer métricas y criterios de aceptación.
