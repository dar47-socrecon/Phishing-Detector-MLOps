# 🛡️ Phishing Detector MLOps

Este repositorio contiene la arquitectura, el código y los pipelines (MLOps) para un sistema de detección de ataques de Phishing basado en Machine Learning (ML). El sistema se centra en el **análisis del contenido textual** de correos electrónicos para detectar indicadores de compromiso (IoC) y técnicas de ofuscación de lenguaje.

El modelo implementado prioriza el **Recall (detección)** de la clase Phishing mediante el uso de la técnica de sobremuestreo **SMOTE** y el ajuste del umbral de decisión.

## 🚀 Estructura del Proyecto

El proyecto sigue una estructura de repositorio estandarizada para proyectos de Data Science/ML:

| Directorio | Descripción |
| :--- | :--- |
| `src/` | **Código de Producción.** Contiene los scripts de entrenamiento (`train_model.py`) y la **lógica de inferencia (`inference_pipeline.py`)**. |
| `data/` | Datos brutos y preprocesados (solo el dataset de entrenamiento y archivos de *split* pequeños). |
| `metrics/` | Resultados de evaluación del modelo (F1-Score, Recall, Curvas ROC, Falsos Negativos). |
| `artifacts/` | Modelos serializados (`logistic_regression_smote_model.pkl`), vectorizadores (`tfidf_vectorizer.pkl`) y mapeo de etiquetas. |
| `requirements.txt`| Dependencias de Python necesarias para replicar el entorno (pandas, scikit-learn, etc.). |
| `notebooks/`| Cuadernos de Colab para la experimentación y evaluación de modelos (`EvaluationsModels_Practical.ipynb`). |

## 🧠 Modelo Clave Implementado

El pipeline actual utiliza:

* **Modelo:** **Regresión Logística** (Rápido y interpretable).
* **Vectorización:** TF-IDF (Term Frequency-Inverse Document Frequency).
* **Mitigación de Riesgo:** **SMOTE** aplicado al set de entrenamiento y un umbral de decisión de **0.40** para minimizar Falsos Negativos (brechas de seguridad).

## ⚙️ Requisitos del Entorno

Para replicar el entorno de entrenamiento y validación:

```bash
Paso 1: Clonar y Preparar el Entorno

```bash
git clone [https://github.com/dar47-socrecon/Phishing-Detector-MLOps.git](https://github.com/dar47-socrecon/Phishing-Detector-MLOps.git)
cd Phishing-Detector-ML
python3 -m venv venv
source venv/bin/activate
