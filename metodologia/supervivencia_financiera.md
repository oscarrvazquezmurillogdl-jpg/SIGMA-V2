# Supervivencia financiera

## Objetivo metodológico

Representar la continuidad financiera-operativa como una trayectoria temporal de recursos líquidos, obligaciones y capacidad real de financiamiento.

El presupuesto funciona como calibración inicial; el centro analítico es la evolución observada y proyectada de la liquidez.

## Capas previstas

### 1. Datos y evidencia

Integra caja, cobranza, pagos, inventarios, proveedores, nómina, impuestos, deuda, CAPEX, ventas, clientes, financiamiento y contingencias. Cada dato requiere fecha, fuente y estado de validación.

### 2. Motor determinístico

Calcula caja final y buffer por periodo. Su función es localizar insuficiencias y dependencias de financiamiento sin atribuir probabilidades no estimadas.

### 3. Escenarios

Evalúa cambios expresamente definidos, por ejemplo:

- retraso de cobranza;
- caída de ventas;
- pérdida de clientes;
- contingencia fiscal;
- restricción de crédito;
- incremento de costos o CAPEX.

Un escenario no es un hecho ni una predicción.

### 4. Validación temporal

Contrasta proyecciones anteriores contra resultados reales. Requiere históricos comparables y evita mezclar información futura dentro del entrenamiento o calibración.

### 5. Capa predictiva

Podrá estimar probabilidades, tiempo hasta un evento o distribución de resultados. Su selección depende de la variable objetivo, el volumen y calidad de los datos y el horizonte aprobado.

## Indicadores candidatos

Se han identificado como candidatos, no como métricas definitivamente aprobadas:

- duración del efectivo o runway;
- velocidad de consumo de caja;
- conversión EBITDA a caja;
- ciclo de conversión de efectivo;
- capital de trabajo;
- sincronización financiera;
- CAPEX;
- dependencia de financiamiento;
- criticidad;
- sensibilidad a retrasos;
- deterioro progresivo;
- ICOT, IAC e IDFO, pendientes de especificación formal.

## Decisiones pendientes

- Frecuencia temporal.
- Horizonte.
- Variable objetivo.
- Definición cuantitativa de eventos.
- Umbrales.
- Prioridad de pagos.
- Tratamiento de datos censurados, faltantes y atípicos.
- Métricas de validación.
- Segmentación por tipo y tamaño de empresa.
