# Reglas para agentes humanos y de IA

## Propósito

Estas reglas controlan cualquier análisis, modificación o generación realizada sobre SIGMA V2.

## Jerarquía de fuentes

1. Datos primarios conciliados y documentados.
2. Reglas aprobadas en este repositorio.
3. Supuestos explícitos autorizados para un escenario.
4. Inferencias identificadas como tales.

Una categoría inferior no puede presentarse como si perteneciera a una superior.

## Reglas obligatorias

- No inventar información, fechas, importes, umbrales, relaciones causales ni evidencia.
- No sustituir un dato faltante con promedios, referencias sectoriales o criterios propios sin autorización explícita.
- Marcar cada dato como observado, calculado, estimado, supuesto o faltante.
- Conservar la unidad monetaria, unidad temporal y procedencia de cada dato.
- Diferenciar liquidez, solvencia, rentabilidad y continuidad operativa.
- No confundir utilidad contable o EBITDA con efectivo disponible.
- No etiquetar como colapso un déficit temporal sin aplicar una definición aprobada.
- No usar machine learning antes de validar la capa determinística y disponer de datos históricos suficientes.
- No incorporar información confidencial de clientes en el repositorio público.

## Proceso mínimo

1. Identificar el objetivo concreto.
2. Inventariar datos disponibles.
3. Declarar faltantes y su efecto.
4. Ejecutar únicamente cálculos autorizados por los datos.
5. Aplicar controles aritméticos, temporales, contables y de trazabilidad.
6. Separar resultados, escenarios e incertidumbre.
7. Emitir una conclusión limitada por la evidencia.

## Formato obligatorio para cada avance

1. **Siguiente paso:** uno solo, realista y ejecutable.
2. **Calculable ahora:** cálculos permitidos con los datos existentes.
3. **Faltantes:** datos, definiciones o evidencia todavía requeridos.
4. **Validación:** prueba, resultado esperado y condición de rechazo.
5. **Artefacto:** archivo, tabla, especificación, prueba o módulo resultante.

## Control de cambios

Toda modificación que cambie fórmulas, definiciones, umbrales o decisiones debe:

- indicar el motivo;
- identificar la evidencia;
- actualizar las pruebas relacionadas;
- registrarse en `CHANGELOG.md`;
- someterse a revisión antes de considerarse parte de la versión oficial.

## Límite actual

El repositorio contiene una arquitectura inicial. No existe todavía evidencia suficiente para declarar validado un modelo predictivo de supervivencia financiera.
