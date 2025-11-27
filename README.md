# Scraping y ML
Extracción de datos históricos (Scraping) y la aplicación de un modelo Random Forest Regressor.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1vytTptHBhI1GMB2nSH1Ulk9OB6OEFhMl?usp=sharing)
> **Nota:** Haz clic en el botón de arriba para abrir el notebook directamente en Google Colab.

---

## Descripción General

Este proyecto implementa un sistema de **análisis predictivo** diseñado para estimar los resultados de partidos de fútbol de la liga española (La Liga). El pipeline cubre todo el proceso de **Data Science**, desde la extracción de datos históricos mediante **Web Scraping** y expresiones regulares, hasta el entrenamiento de un modelo de **Machine Learning** para generar predicciones.

## Objetivo

Predecir los marcadores finales de los partidos de fútbol no jugados de la temporada, basándose en un amplio conjunto de datos históricos de resultados de La Liga Española.

---

## Tecnología y Metodología

Esta sección destaca las herramientas y técnicas clave utilizadas en el desarrollo del proyecto.

### 1. Extracción de Datos (Scraping)

* **Fuente:** Datos históricos de resultados de partidos de fútbol de la web de AS.
* **Técnica:** Se utiliza la librería `urllib.request` de Python para obtener el contenido HTML de múltiples temporadas.
* **Procesamiento:** El corazón de la extracción se basa en el uso de **expresiones regulares (RegEx)** adaptadas a los distintos formatos HTML de la web a lo largo de los años para aislar nombres de equipos y marcadores.

### 2. Preparación y Modelado

* **Librerías Clave:** `Pandas`, `Numpy`, `Scikit-learn`.
* **Preprocesamiento:**
    * Los datos se estructuran en **Pandas DataFrames**.
    * Se aplica **One-Hot Encoding** a las variables categóricas (nombres de equipos) para transformarlas en un formato numérico que el modelo pueda interpretar.
* **Modelo de Machine Learning:**
    * **Modelo:** **Random Forest Regressor** (`sklearn.ensemble.RandomForestRegressor`).
    * **Métrica de Evaluación:** El rendimiento del modelo se evalúa utilizando el **Error Absoluto Mediano** (`median_absolute_error`) sobre el conjunto de prueba (`test`).

---

## Resultados Clave

El modelo de **Random Forest Regressor** se entrenó con los datos históricos para generar la predicción de goles.

* **Precisión:** El modelo se evalúa utilizando el Error Absoluto Mediano (Median Absolute Error - MAE). (0.8325).
* **Salida Final:** El notebook genera un listado de los partidos restantes de la temporada con la predicción del marcador para cada encuentro, con el formato: `[Equipo Local] [Predicción de goles local] - [Predicción de goles visitante] [Equipo Visitante]`.

---

## Estructura del Notebook

1.  **Extracción de datos (Scraping):** Obtención y limpieza de datos históricos.
2.  **Preparación y modelado de datos:** Carga a Pandas, **One-Hot Encoding** y división de sets de entrenamiento/prueba.
3.  **Entrenamiento y Resultados:** Implementación del **Random Forest Regressor** y evaluación del MAE.
4.  **Anexo:** Re-entrenamiento con todos los datos históricos para generar la predicción final de partidos no jugados.
