# Criterios de validación

## Principio

Un resultado no se considera validado solo porque el programa se ejecute. Debe superar controles de datos, cálculo, trazabilidad y desempeño temporal.

## Pruebas mínimas

### 1. Integridad estructural

- Verificar presencia y tipo de los campos requeridos.
- Rechazar registros sin fecha, moneda, fuente o estado de evidencia.
- No convertir vacíos a cero automáticamente.

### 2. Conciliación

- Comparar caja inicial con bancos y caja conciliados a la fecha de corte.
- Comparar entradas y salidas realizadas con evidencia contable y bancaria.
- La tolerancia monetaria está pendiente de aprobación.

### 3. Identidad aritmética

Para cada periodo debe cumplirse la fórmula aprobada de caja final. Cualquier diferencia no explicada rechaza el cálculo.

### 4. Continuidad temporal

La caja final del periodo `t` debe coincidir con la caja inicial del periodo `t+1`, salvo ajuste conciliado y documentado.

### 5. Trazabilidad

Todo importe debe conducir a una fuente. Un dato sin evidencia debe conservar una etiqueta que impida tratarlo como observado.

### 6. Separación de escenarios

El caso base y cada escenario deben calcularse y presentarse por separado.

### 7. Backtesting

Cuando existan históricos:

1. fijar una fecha de corte pasada;
2. usar solo información disponible hasta esa fecha;
3. producir la proyección;
4. compararla con resultados posteriores;
5. registrar error, sesgo y estabilidad.

Las métricas y umbrales de aceptación están pendientes.

### 8. Sensibilidad

Modificar únicamente una variable autorizada y verificar que el resultado cambie en la dirección económicamente coherente. Esta prueba detecta errores de signo o lógica, pero no demuestra precisión predictiva.

## Resultado de validación

Cada ejecución debe terminar como:

- **Aceptada:** cumple todos los controles obligatorios aplicables.
- **Aceptada con limitaciones:** calcula, pero existen restricciones explícitas que no invalidan la operación realizada.
- **Rechazada:** falla integridad, conciliación, aritmética, continuidad, trazabilidad o una condición de aceptación aprobada.

No debe utilizarse la categoría «Aceptada» mientras falten tolerancias y criterios requeridos para la prueba correspondiente.
