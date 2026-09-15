# SIGMA V2

**Modelo predictivo de supervivencia financiera y riesgo de liquidez empresarial**

## Estado del proyecto

SIGMA V2 se encuentra en fase de arquitectura metodológica. Este repositorio documenta el modelo, los datos requeridos, las reglas de ejecución y los criterios de validación.

**Todavía no constituye un modelo validado para producción ni contiene información real de empresas.**

## Pregunta central

> ¿En qué fecha futura una empresa dejará de disponer de liquidez suficiente para continuar operando, bajo datos, reglas y supuestos expresamente documentados?

## Punto de partida

La primera capa de SIGMA V2 es determinística. Antes de incorporar machine learning debe existir un motor reproducible que proyecte la liquidez por periodo.

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

Un valor de `Buffer_t < 0` identifica insuficiencia de liquidez bajo las reglas y el periodo analizados. Su interpretación como deterioro, insolvencia operativa o colapso requiere definiciones y umbrales aprobados.

## Principios obligatorios

1. No inventar datos, umbrales, supuestos ni evidencia.
2. Separar hechos observados, cálculos, estimaciones y escenarios.
3. Declarar explícitamente cualquier dato faltante.
4. Mantener trazabilidad entre cada dato y su fuente.
5. No presentar como predicción validada un cálculo determinístico no contrastado.
6. Validar el modelo antes de utilizarlo para decisiones empresariales.
7. No almacenar datos confidenciales o identificables de clientes en este repositorio público.

## Qué puede definirse actualmente

- Arquitectura de datos.
- Identidades matemáticas del flujo de caja.
- Reglas de trazabilidad y control.
- Pruebas de integridad, conciliación y consistencia.
- Estructura de escenarios y validación.
- Formato del artefacto semanal de avance.

## Qué todavía requiere datos o decisión

- Unidad temporal y horizonte de proyección.
- Definición cuantitativa de caja mínima operativa.
- Reglas de prioridad y diferimiento de pagos.
- Disponibilidad efectiva de las líneas de crédito.
- Umbrales formales de tensión, insolvencia operativa, muerte funcional y colapso.
- Históricos suficientes para calibración y backtesting.
- Tolerancias de conciliación y criterios estadísticos de aceptación.
- Tratamiento de impuestos, CAPEX, deuda, contingencias y estacionalidad por tipo de empresa.

## Estructura

```text
SIGMA-V2/
├── README.md
├── AGENTS.md
├── INSTRUCCION_MAESTRA.md
├── CHANGELOG.md
├── metodologia/
│   ├── supervivencia_financiera.md
│   └── definiciones_operativas.md
├── datos/
│   ├── diccionario_de_datos.md
│   └── plantilla_entrada.csv
├── validacion/
│   ├── criterios_de_validacion.md
│   └── casos_de_prueba.md
└── src/
    └── README.md
```

## Uso previsto

1. Leer esta introducción.
2. Aplicar `INSTRUCCION_MAESTRA.md`.
3. Respetar `AGENTS.md` cuando intervenga una IA.
4. Completar el diccionario y la plantilla exclusivamente con datos documentados.
5. Ejecutar las validaciones antes de interpretar resultados.
6. Registrar cada modificación metodológica en `CHANGELOG.md`.

## Confidencialidad

Este repositorio es público. Solo debe contener metodología, código, plantillas vacías y casos sintéticos claramente identificados. Los datos reales de clientes deben permanecer fuera del repositorio y sujetarse a controles de acceso, confidencialidad y protección de datos.

## Licencia

No se ha definido una licencia. La visibilidad pública permite consultar el contenido, pero no establece por sí misma condiciones de reutilización, modificación o distribución.
