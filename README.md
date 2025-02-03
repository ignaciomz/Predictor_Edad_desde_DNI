📌 Predicción de Edad a partir del DNI

🏆 Objetivo del Proyecto

Este proyecto tiene como objetivo predecir la edad de una persona a partir de su número de DNI (Documento Nacional de Identidad) Argentino. Se entrenó un modelo de Machine Learning con más de 400,000 registros para hacer estimaciones basadas en patrones detectados en los DNIs.

🛠️ Metodología y Modelo Usado

Se utilizó Random Forest Regressor, un modelo de aprendizaje automático basado en árboles de decisión.

Se entrenó con un conjunto de datos reales que incluye DNIs y edades calculadas a partir de la fecha de nacimiento.

El modelo aprende relaciones implícitas entre los DNIs y las edades, permitiendo hacer estimaciones precisas.

Se obtuvo un error absoluto medio cercano a 0.39.

📂 Datos Utilizados

El dataset de entrenamiento contiene las siguientes columnas:

DNI: Número de documento de identidad argentino.

Edad: Edad real calculada a partir de la fecha de nacimiento.

🔥 Cómo Usar el Modelo Entrenado

Descargar el modelo entrenado

Cargarlo en Python

import joblib
modelo = joblib.load("modelo_edad_dni.pkl")

nuevo_dni = [[xxxxxxxx]]  # Reemplazar con el DNI deseado

edad_predicha = modelo.predict(nuevo_dni)
print(f"Edad estimada: {edad_predicha[0]:.2f} años")

--Ejecutarlo en Google Colab (si no tienes Python localmente)

--Sube el archivo modelo_edad_dni.pkl a tu Google Drive.

--Usa drive.mount('/content/drive') para acceder a él en Colab.

📥 Predicción en Masa

Si tienes un archivo con una lista de DNIs nuevos y quieres predecir sus edades, puedes usar un script adicional que procesa un archivo de Excel o CSV con DNIs y devuelve la edad estimada para cada uno.

import pandas as pd

archivo_nuevos_dnis = "nuevos_dnis.xlsx"  # Cambiar por el nombre del archivo
nuevos_dnis = pd.read_excel(archivo_nuevos_dnis)

nuevos_dnis["Edad_Predicha"] = modelo.predict(nuevos_dnis[["DNI"]])

nuevos_dnis.to_excel("predicciones.xlsx", index=False)
