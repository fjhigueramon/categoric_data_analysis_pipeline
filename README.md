# Categoric Data Analysis Pipeline

## Descripción

Este proyecto implementa una metodología para el análisis de datos categóricos utilizando técnicas de Procesamiento del Lenguaje Natural (NLP) y Aprendizaje Automático (Machine Learning).

La herramienta ha sido desarrollada como parte de un Trabajo Fin de Grado (TFG) centrado en la identificación de perfiles de consumidores energéticos mediante técnicas de clustering, análisis semántico y explicabilidad de modelos.

Las principales funcionalidades incluyen:

* Generación de embeddings mediante modelos Sentence-BERT.
* Reducción de dimensionalidad utilizando PCA y UMAP.
* Clustering mediante K-Means y HDBSCAN.
* Modelado de temas mediante BERTopic.
* Validación supervisada mediante Random Forest.
* Explicabilidad de resultados mediante SHAP.
* Exportación automática de resultados y visualizaciones.

---

## Instalación

### Crear entorno virtual

```bash
python -m venv venv
```

### Activar entorno virtual

Windows:

```bash
venv\Scripts\activate
```

Linux / MacOS:

```bash
source venv/bin/activate
```

### Instalar dependencias

```bash
pip install -r requirements.txt
```

---

## Requisitos

* Python 3.11 o superior.
* Desarrollado y probado con Python 3.13.

---

## Estructura del proyecto

```text
project/
│
├── data/
    ...
│   ├── datos_dimensiones.csv
│   ├── datos_clusterizados.csv
│   └── datos_rf.csv
│
├── results/
    ...
│   ├── resultados_kmeans.csv
│   ├── importancia_variables.png
│   └── shap/
│       ├── shap_cluster_0.png
│       ├── shap_cluster_1.png
│       └── shap_cluster_2.png
│
├── pipeline.py
├── requirements.txt
└── README.md
```

---

## Formato de entrada

El dataset debe contener al menos las siguientes columnas:

| Columna         | Descripción                          |
| --------------- | ------------------------------------ |
| user_id         | Identificador único del usuario      |
| respuestas_norm | Respuesta normalizada de la encuesta |

Opcionalmente pueden incluirse columnas adicionales relacionadas con dimensiones o categorías temáticas.

---

## Funcionalidades disponibles

### Opción 1 - Pipeline completo

Ejecuta el flujo completo de análisis:

* Generación de embeddings.
* Reducción dimensional (PCA + UMAP).
* Clustering mediante K-Means.
* Exportación de resultados.

Ficheros generados:

* datos_clusterizados.csv
* datos_rf.csv
* resultados_kmeans.csv

---

### Opción 2 - Clustering K-Means

Permite ejecutar únicamente la fase de clustering mediante K-Means.

---

### Opción 3 - HDBSCAN

Aplica clustering basado en densidad utilizando HDBSCAN.

---

### Opción 4 - BERTopic

Realiza análisis semántico de respuestas abiertas mediante BERTopic.

Resultados obtenidos:

* Temas detectados.
* Palabras clave asociadas.
* Visualizaciones interactivas.

---

### Opción 5 - Visualización UMAP

Genera representaciones visuales de los clusters obtenidos mediante reducción dimensional.

---

### Opción 6 - Random Forest + SHAP

Valida los perfiles obtenidos mediante clustering utilizando un clasificador Random Forest.

Resultados generados:

* Accuracy.
* Precision, Recall y F1-score.
* Importancia de variables.
* Gráficos SHAP por perfil.

Archivos exportados:

```text
results/
├── importancia_variables.png
└── shap/
```

---

## Flujo recomendado

```text
1. Ejecutar Pipeline completo
          ↓
2. Generar perfiles de usuario
          ↓
3. Exportar datos_rf.csv
          ↓
4. Ejecutar Random Forest + SHAP
          ↓
5. Analizar variables relevantes
```

---

## Tecnologías utilizadas

* Python
* Sentence Transformers
* BERT
* BERTopic
* UMAP
* HDBSCAN
* K-Means
* Random Forest
* SHAP
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib

---

## Autor

Francisco J. Higuera Montero

