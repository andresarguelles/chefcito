# Detección y Clasificación de Vocalizaciones Ultrasonicas

Este proyecto tiene como objetivo procesar, analizar y clasificar vocalizaciones ultrasonicas (USVs) para detectar la presencia de ratas y diferenciarlas de otros sonidos en rangos ultrasónicos. El sistema utiliza técnicas de procesamiento de señales para extraer características relevantes de las vocalizaciones y entrenar un modelo de Machine Learning basado en el algoritmo de clasificación K-Nearest Neighbors (KNN). Este modelo permite determinar si una vocalización corresponde a una rata o no.

## Funcionalidades principales

1. **Lectura y preprocesamiento de audio**:
   - Carga de archivos de audio en formato `.wav`.
   - Normalización y centrado de las señales de audio.

2. **Filtrado pasabanda**:
   - Aplicación de un filtro pasabanda para aislar frecuencias ultrasónicas entre 20 kHz y 90 kHz.

3. **Análisis espectral**:
   - Cálculo de la Transformada Rápida de Fourier (FFT) para analizar la energía espectral de las señales.
   - Visualización de las señales en el dominio del tiempo y de las frecuencias.

4. **Detección de sílabas**:
   - División de la señal filtrada en ventanas de 5 ms.
   - Identificación de ventanas activas basadas en la energía espectral.
   - Agrupación de ventanas consecutivas para detectar sílabas.
   - Fusión de sílabas separadas por menos de 21 ms.

5. **Extracción de características**:
   - Cálculo de características como frecuencia central media, frecuencia máxima, frecuencia mínima, energía total y modulación.
   - Almacenamiento de las características extraídas en un archivo CSV (`caracteristicas_silabas.csv`).

6. **Entrenamiento y clasificación con KNN**:
   - Uso de las características extraídas para entrenar un modelo de clasificación supervisada basado en KNN.
   - Clasificación de las sílabas detectadas para determinar si corresponden a ratas o no.

7. **Visualización**:
   - Comparación gráfica de la señal original y la señal filtrada.
   - Generación de espectrogramas para analizar patrones temporales y frecuenciales.
   - Visualización de los resultados de clasificación.

## Archivos generados

- `detalles_silabas.csv`: Contiene información sobre las sílabas detectadas, incluyendo su inicio, fin y duración.
- `caracteristicas_silabas.csv`: Contiene las características extraídas de cada sílaba detectada.
- `resultados_clasificacion.csv`: Contiene las predicciones del modelo KNN para cada sílaba detectada.

## Requisitos

- Python 3.x
- Bibliotecas necesarias:
  - `numpy`
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `librosa`
  - `scipy`
  - `scikit-learn`

## Uso

1. Coloca los archivos de audio en la carpeta `dataset/`.
2. Ejecuta el programa para procesar los archivos de audio y extraer las características de las sílabas.
3. Entrena el modelo KNN con un conjunto de datos etiquetado que incluya vocalizaciones de ratas y otros sonidos en rangos ultrasonicos similares.
4. Clasifica nuevas vocalizaciones y revisa los resultados en los archivos CSV generados y las visualizaciones gráficas.

## Aplicaciones

Este sistema puede ser utilizado para detectar la presencia de ratas en un entorno específico a través de sus vocalizaciones. Esto puede ser útil en monitoreo y control de plagas.

## Licencia

Este proyecto está licenciado bajo la [MIT License](LICENSE).