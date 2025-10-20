# 🏙️ Análisis de Criminalidad en Chicago: EDA, Imputación y Modelado Predictivo

## 1\. Contexto y Objetivos del Proyecto

Este proyecto realiza un análisis exploratorio de datos (EDA) del conjunto **Crimes – 2001 to Present**, que incluye más de **8.4 millones** de incidentes reportados a la policía de Chicago. El objetivo es identificar patrones temporales, espaciales, y preparar el terreno para aplicar modelos de *Machine Learning* para la predicción de arrestos.

### Objetivos Principales:

Realizar un Análisis Exploratorio de Datos (EDA) del conjunto de crímenes de Chicago (2001–actualidad), complementado con modelos de *Machine Learning*, para identificar patrones temporales, espaciales y factores asociados a los arrestos.

1. Analizar las tendencias de criminalidad en Chicago durante el periodo 2001–2025, destacando los cambios relacionados con eventos socioeconómicos relevantes.
2. Identificar los factores que influyen en la probabilidad de que un delito concluya en un arresto mediante la aplicación de modelos de clasificación supervisada.
3. ¿Dónde se concentran los delitos en Chicago y cómo han cambiado los hotspots geográficos a lo largo del tiempo?
-----

## 2\. Requisitos y Configuración del Entorno

Para ejecutar el análisis, necesita **Python 3.11** (recomendado) y las siguientes dependencias.

### 2.1. Archivos Requeridos

Asegúrese de que los siguientes archivos estén en la carpeta raíz del proyecto:

| Archivo | Descripción |
| :--- | :--- |
| **`Data_Analitycs.ipynb`** | El *Jupyter Notebook* que contiene todo el código de análisis. |
| **`Crimes_Chicago_full.csv`** | El archivo de datos original de Chicago Police Department. |
| **`Data_Analitycs.pdf`** y **`Data_Analitycs.html`** | Archivos opcionales que contienen la ejecución completa del *notebook* para solo visualización. |

### 2.2. Dependencias (`requirements.txt`)

Cree un archivo llamado `requirements.txt` con las siguientes librerías:

```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
contextily
folium
hdbscan
```

### 2.3. Instalación Paso a Paso

1.  **Cree y Active el Entorno Virtual:**

    ```bash
    # 1. Cree el entorno (use python3.11 o su versión disponible)
    python3.11 -m venv venv_chicago

    # 2. Active el entorno
    source venv_chicago/bin/activate
    ```

2.  **Instale las Dependencias:**

    ```bash
    pip install -r requirements.txt
    ```

-----

## 3\. Ejecución y Visualización del Análisis

### 3.1. Opción A: Ejecutar el Código Interactivamente (Recomendado)

Si desea modificar el código o correr las celdas usted mismo:

1.  **Inicie el Servidor Jupyter:**

    ```bash
    jupyter lab
    # Opcional: jupyter notebook
    ```

2.  **Ejecute el Notebook:**

      * Abra el archivo `Data_Analitycs.ipynb` en su navegador.
      * Ejecute todas las celdas en orden: `Cell` -\> **`Run All`**.

### 3.2. Opción B: Visualizar los Resultados (Acceso Rápido)

**Si no desea instalar dependencias ni ejecutar el código,** puede ver el resultado final del análisis y todas las visualizaciones generadas:

  * Abra directamente el archivo **`Data_Analitycs.pdf`** o **`Data_Analitycs.html`** en su navegador o visor de documentos.

-----

## 4\. Hallazgos y Fases del Análisis

El *notebook* se estructura en las siguientes fases metodológicas:

| Fase del Análisis | Descripción y Método | Resultados Clave |
| :--- | :--- | :--- |
| **I. Limpieza y Preparación** | Manejo de 8.4M de registros. Eliminación de nulos en coordenadas (1.11%). | Se garantiza un *dataset* limpio para el análisis geográfico y temporal. |
| **II. Imputación Geográfica** | Imputación del 7.18% de nulos en `Community Area` usando **K-Nearest Neighbors (KNN)**. | **Validación Exitosa:** `Accuracy` de imputación del **99.32%**, asegurando la calidad de los datos espaciales. |
| **III. EDA y Tendencias** | Análisis de `Primary Type`, `Year`, `Hour` y `Season`. | **Tendencia Histórica:** Caída sostenida de incidentes desde el pico de 2002. **Patrones Cíclicos:** Los crímenes son máximos en **Verano** y en las horas **de la tarde**. **Tipología:** El **Robo (THEFT)** es el delito más común. |

-----

*Para salir del entorno virtual al finalizar su trabajo, use el comando `deactivate` en su terminal.*