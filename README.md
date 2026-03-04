# telecom-churn-prediction
# 📊 Predicción de Abandono (Churn) en Telecomunicaciones

Este proyecto utiliza técnicas de análisis de datos y Machine Learning para identificar los factores que influyen en la pérdida de clientes en una empresa de telecomunicaciones.

## 🚀 Objetivo del Proyecto
Analizar el comportamiento de los clientes y preparar un dataset para entrenar un modelo que prediga si un usuario cancelará su servicio (*Churn*).

## 🛠️ Tecnologías Utilizadas
* **Python** (Pandas, NumPy, Matplotlib, Seaborn)
* **Jupyter Notebook**
* **Google Colab**

## 📈 Pasos Realizados
1. **Limpieza de Datos:** Tratamiento de valores nulos y normalización de columnas anidadas.
2. **Feature Engineering:** Conversión de variables categóricas y booleanas a formatos numéricos (`int64`, `float64`).
3. **Análisis Exploratorio (EDA):** Visualización de la relación entre cargos mensuales, tipo de contrato y el abandono.

## 📂 Estructura del Repositorio
* `Proyecto_telecom_2.ipynb`: Cuaderno principal con todo el proceso de limpieza y análisis

## 📊 Resultados del Modelo
Se evaluaron varios algoritmos, siendo el **Random Forest** el seleccionado debido a su equilibrio entre precisión y detección de fugas (Recall).

| Modelo | Recall (Detecta fugas) | Precision (Acierto en alertas) |
|--------|-----------------|-------------------------|
| **Random Forest** | **48%** | **67%** |
| Regresión Logística | 52% | 65% |
| Árbol de Decisión | 52% | 60% |

## 💡 Hallazgos Principales
* **Contratos Mensuales:** Son el factor de mayor riesgo; los clientes sin permanencia tienden a irse más rápido.
* **Cargos Mensuales:** Clientes con facturas superiores a **$80** tienen una probabilidad significativamente mayor de abandonar.
* **Fibra Óptica:** Existe una correlación alta entre el servicio de fibra y el Churn, lo que sugiere revisar la calidad del servicio técnico en esa área.

## 🛠️ Cómo usar el modelo entrenado
Si deseas usar el modelo predictivo sin necesidad de entrenarlo de nuevo, puedes cargarlo en Python de la siguiente manera:

```python
import pickle

# Cargar el modelo desde el archivo .pkl
with open('modelo_random_forest.pkl', 'rb') as file:
    modelo = pickle.load(file)

# Realizar una predicción
# prediccion = modelo.predict(nuevos_datos)
