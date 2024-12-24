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
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad.
- *Unfreeze* de las 2 últimas capas del modelo preentrenado. Es decir, entrenaré las 2 últimas capas de la base convolucional de VGG16.
- 3 capas densas:
  - 500 neuronas, 100 neuronas, 2 neuronas (clases a predecir: presencia o no presencia)
- Capas de dropout:
  - 2 capas de dropout (0.5), luego de las capas densas, a excepción de la capa de salida.

-----

# 2) Comparativa de rendimiento

### 2.1) Métricas de rendimiento
Aquí se compara la métrica clave para ambos modelos:

| Métrica      | Modelo sin Fine-Tuning | Modelo con Fine-Tuning |
|--------------|------------------------|------------------------|
|  Accuracy    | 92.64%                 | 95.67%                 |


### 2.2) Gráficas de desempeño
- Modelo sin Fine-Tuning:
  - Accuracy: Training vs Validation 
    ![Accuracy](link)

  - Loss: Training vs Validation
    ![Loss](link)

- Modelo con Fine-Tuning:
  - Accuracy: Training vs Validation
    ![Accuracy](link)

  - Loss: Training vs Validation
    ![Loss](link)

-----

# 3) Ejemplos de predicciones:

### 3.1.1) Modelo sin Fine-Tuning

- Imagen con presencia de retinopatía diabética:
  
![Presencia-RD](https://github.com/DianaMLlamocaZ/CLASIFICACION_IMAGENES/blob/main/ComputerVision-DIABETIC_RETINOPATHY/Imagenes-Prueba/Modelo-NoFT-DA-RD.JPG)

- Imagen con no presencia de retinopatía diabética:
  
![](NoPresencial-RD)(https://github.com/DianaMLlamocaZ/CLASIFICACION_IMAGENES/blob/main/ComputerVision-DIABETIC_RETINOPATHY/Imagenes-Prueba/Modelo-NoFT-DA-RD.JPG)


### 3.1.2) Modelo con Fine-Tuning
![]()
