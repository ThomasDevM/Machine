# Proyecto de Machine Learning – Segmentación Avanzada para Riesgo Crediticio

##  Descripción General
Este proyecto tiene como objetivo realizar una **segmentación avanzada de clientes** en un contexto de **riesgo crediticio**, utilizando técnicas de *Machine Learning no supervisado*. El análisis busca identificar **patrones latentes de comportamiento financiero** que permitan enriquecer modelos de scoring crediticio posteriores.

La metodología se centra en el algoritmo **K-Means Clustering**, aplicado sobre un conjunto de variables financieras y socioeconómicas previamente procesadas, normalizadas y validadas.

El resultado final no pretende reemplazar un modelo supervisado de clasificación, sino **potenciarlo mediante ingeniería de características**, incorporando el identificador de clúster como una variable contextual adicional.

---

##  Metodología Utilizada
El desarrollo del proyecto sigue una estructura inspirada en **CRISP-DM**, adaptada a un flujo práctico en notebook:

1. **Comprensión del problema**: Segmentación de clientes según perfiles de riesgo.
2. **Comprensión de los datos**: Exploración inicial y validación de consistencia.
3. **Preparación de datos**:
   - Limpieza de valores nulos
   - Escalamiento de variables numéricas (StandardScaler)
   - Selección de variables relevantes
4. **Modelado**:
   - Algoritmo K-Means
   - Determinación del número óptimo de clústeres mediante el Método del Codo
5. **Evaluación**:
   - Análisis visual de clústeres
   - Proyección de datos mediante PCA
6. **Interpretación**:
   - Identificación de segmentos de solvencia y vulnerabilidad
   - Análisis estratégico para su integración futura en modelos supervisados

---

##  Estructura del Proyecto

```text
Para la ejecución correcta del código debe estar subido en un drive con la siguiente estructura
.
├──Semestre6
   ├──Machine
   ├──├── EVA3.ipynb              # Notebook principal con el flujo completo del proyecto
      ├── README.md               # Documento de descripción y reproducibilidad
      └── datos_examen/                   # Carpeta local esperada para los datasets 
```

---

##  Dataset


Los archivos se encuentran disponibles en Google Drive:

 **Enlace al dataset**: https://drive.google.com/drive/folders/1LMztfx2_ni6SI0a-bK9kpPpbDNehw8bg?hl=es_419

### Estructura esperada de los datos

```text
data/
├── application_train.parquet
├── bureau.parquet
├── bureau_balance.parquet
├── previous_application.parquet
├── installments_payments.parquet
```

El notebook está diseñado para ser **100% reproducible** una vez que los archivos se descargan y se ubican en la carpeta `datos_examen/`.

---

##  Requisitos del Entorno

El proyecto fue desarrollado utilizando **Python 3.x** y las siguientes librerías:

- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn

Instalación rápida:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
```

---

##  Instrucciones de Ejecución

1. Clonar el repositorio.
2. Descargar los archivos `.parquet` desde Google Drive.
3. Colocar los archivos en la carpeta `data/`.
4. Abrir el archivo `EVA3.ipynb`.
5. Ejecutar las celdas **en orden secuencial** para asegurar la correcta reproducción del pipeline.

---

##  Resultados Principales

- Se identificaron **segmentos diferenciados de clientes**, con patrones claros de estabilidad y vulnerabilidad financiera.
- Algunos clústeres presentan una **mayor concentración de incumplimiento**, validando su utilidad como señal de riesgo.
- La proyección mediante **PCA** permitió confirmar visualmente la separación entre perfiles.

---

##  Integración con Modelos Supervisados

El identificador de clúster (`cluster_id`) puede ser incorporado como una **feature categórica** en modelos supervisados como:

- XGBoost
- LightGBM
- Random Forest

Esto permite:
- Diseñar **políticas de aprobación diferenciadas**
- Mejorar la **capacidad predictiva** del scoring
- Aportar interpretabilidad estratégica al negocio

---

##  Limitaciones y Trabajo Futuro

- K-Means asume clústeres de forma esférica; se recomienda evaluar métricas adicionales como **Silhouette Score**.
- El modelo es sensible a outliers, por lo que futuras iteraciones podrían incorporar técnicas de filtrado más robustas.
- Comparar el desempeño de un modelo supervisado con y sin `cluster_id` para cuantificar la ganancia real en AUC-ROC.

---

##  Integrantes

- Thomas Barrios
- Demis Díaz

---

##  Contexto Académico

Proyecto desarrollado para la asignatura **Machine Learning**, como parte de la evaluación práctica del curso.

