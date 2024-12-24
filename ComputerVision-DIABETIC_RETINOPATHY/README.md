# Detección de retinopatía diabética, mediante imágenes, usando redes neuronales convolucionales
Este proyecto se basa en la detección de retinopatía diabética, mediante imágenes, haciendo uso de una red neuronal convolucional preentrenada, VGG16:
- Red entrenada con fine-tuning
- Red entrena sin fine-tuning

**Importante:**
* Evaluación de ambos modelos en base a su rendimiento.
* Desarrollo de una página web en Streamlit para cargar las imágenes y predicción.

**Datos utilizados:**
- Diagnosis of Diabetic Retinopathy: [https://www.kaggle.com/datasets/pkdarabi/diagnosis-of-diabetic-retinopathy/data]

-----

# 1) Comparación de modelos : Fine-Tuning vs Feature Extraction

### 1.1) Modelo sin Fine-Tuning
El modelo sin fine-tuning se entrenó utilizando el modelo VGG16.

#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad.
- 3 capas densas:
  - 500 neuronas, 100 neuronas, 2 neuronas (clases a predecir: presencia o no presencia)
- Capas de dropout:
  - 2 capas de dropout (0.5), luego de las capas densas, a excepción de la capa de salida.


### 1.2) Modelo con Fine-Tuning
