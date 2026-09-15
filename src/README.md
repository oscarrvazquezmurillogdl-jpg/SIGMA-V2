# Implementación

La implementación ejecutable se pospone hasta aprobar los siguientes elementos:

1. granularidad temporal;
2. horizonte de proyección;
3. diccionario de datos definitivo;
4. caja mínima operativa;
5. reglas de prioridad y diferimiento;
6. definiciones cuantitativas de eventos;
7. tolerancias de validación;
8. casos sintéticos con resultados esperados.

## Primer módulo previsto

El primer `main.py` deberá:

- cargar la plantilla autorizada;
- validar estructura, tipos, fechas, moneda y evidencia;
- rechazar vacíos obligatorios sin convertirlos en cero;
- calcular caja final y buffer;
- comprobar continuidad temporal;
- separar escenarios;
- producir una bitácora reproducible;
- ejecutar pruebas automatizadas.

No deberá incorporar machine learning ni emitir una fecha de colapso validada mientras no se satisfagan los requisitos anteriores.
