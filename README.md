# Simulación de tráfico vehicular con HMM

Cuaderno de Jupyter para comparar una simulación de tráfico normal con otra
en la que se introduce un incidente vial entre las 08:00 y las 11:00.

El modelo utiliza tres estados ocultos (tráfico fluido, moderado y congestionado)
y tres observaciones (velocidad alta, media y baja). Simula 48 períodos de
30 minutos, decodifica una secuencia con Viterbi y presenta métricas y gráficos
comparativos.

## Contenido

- `Simulacion_Trafico_HMM_Modificado.ipynb`: cuaderno de simulación y análisis.
- `requirements.txt`: dependencias para ejecutarlo localmente.
- `.gitignore`: archivos temporales que Git debe ignorar.

## Cómo ejecutarlo en Google Colab

1. Abre Google Colab.
2. Selecciona **Archivo → Subir cuaderno**.
3. Elige `Simulacion_Trafico_HMM_Modificado.ipynb`.
4. Ejecuta las celdas en orden con **Entorno de ejecución → Ejecutar todas**.

## Cómo ejecutarlo localmente

Necesitas Python 3.10 o posterior.

1. Crea y activa un entorno virtual.
2. Instala dependencias con `python -m pip install -r requirements.txt`.
3. Abre el cuaderno con Jupyter: `jupyter notebook`.
4. Abre el archivo `Simulacion_Trafico_HMM_Modificado.ipynb` y ejecuta las celdas de arriba hacia abajo.

## Qué representa la simulación

Los datos son sintéticos: no proceden de sensores ni de una ciudad real.
La velocidad se genera a partir de categorías discretas y las matrices
probabilísticas indicadas en el cuaderno. La comparación permite observar cómo
un cambio en la matriz de transición afecta una corrida simulada.

## Limitaciones conocidas

- La simulación del incidente usa una matriz de transición distinta, pero la
  función Viterbi siempre decodifica con la matriz base. Por eso la detección
  del incidente no está modelada con una matriz dinámica.
- El cuaderno no calcula métricas de precisión de Viterbi frente a los estados
  reales simulados.
- Las emisiones son factores promedio supuestos en g/km según el estado. No
  representan emisiones totales de una ciudad: faltan volumen de vehículos,
  distancia recorrida y calibración con datos locales.
- Las horas del incidente incluyen los pasos 16 a 22, ambos inclusive; son
  siete mediciones de media hora, contando la medición de las 11:00.
- El análisis no implementa rutas alternativas ni un pronóstico de tráfico.

Antes de presentar los resultados como evidencia de tráfico real, se recomienda
corregir o documentar estos puntos y validar el modelo con datos medidos.

## Reproducibilidad

El cuaderno fija semillas de números aleatorios para hacer reproducible la
simulación. Si cambias las semillas o las matrices, pueden cambiar los resultados.

## Licencia y autoría

Pendientes de definir antes de publicar: autoría, afiliación académica y licencia
de uso. No se asignó una licencia automáticamente.
