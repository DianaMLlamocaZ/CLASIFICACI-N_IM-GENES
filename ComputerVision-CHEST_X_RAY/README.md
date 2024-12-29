# Detección de neumonía mediante rayos X de tórax
Este proyecto se basa en la detección de neumonía mediante imágenes de rayos X de pacientes sanos frente a los afectados por neumonía.
- Red entrenada con fine-tuning
- Red entrena sin fine-tuning

**Importante:**
* Evaluación de modelos en base a su rendimiento.

**Datos utilizados:**
- Chest X-Ray-Dataset: [https://www.kaggle.com/datasets/praveengovi/coronahack-chest-xraydataset]

-----

# 1) Comparación de modelos : Fine-Tuning vs Feature Extraction

### 1.1) Modelo sin Fine-Tuning, no class weight, L2 regularization
El modelo sin fine-tuning se entrenó utilizando el modelo VGG16.

#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)

### 1.2) Modelo sin Fine-Tuning, sí classweight, L2 regularization
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad y class weight para el desbalanceo de clases.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)

### 1.3) Modelo no Fine-Tuning, sí classweight, L2 regularization, Dropout
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad y class weight para el desbalanceo de clases.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)
- Capa dropout (30%)
- Batch normalization

### 1.4) Modelo no Fine-Tuning, sí classweight, L2 regularization, Dropout
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad y class weight para el desbalanceo de clases.
- Unfreeze de las 2 últimas capas del modelo VGG16 --> última capa convolucional: block5_conv3 (Conv2D)
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)
- Capa dropout (30%)
- Batch normalization

-----

# 2) Comparativa de rendimiento

### 2.1) Métricas de rendimiento
Aquí se compara la métrica clave para los diferentes modelos entrenados:

| Métrica    |       NO F-T, NO C-W, L2      |     NO F-T, SÍ C-W, L2        |      NO F-T, SÍ C-W, L2, Dropout       |    SÍ F-T, SÍ C-W, L2, Dropout        |
|------------|-------------------------------|-------------------------------|----------------------------------------|---------------------------------------|
|  Accuracy  | 80.12%                        | 84.61%                        | 81.25%                                 | 85.89%                                |
| Specificity| 49.57%                        | 60.25%                        | 50.85%                                 | 64.10%                                |
|  F1_Score  | 86.09%                        | 88.96%                        | 86.89%                                 | 89.76%                                |

**F-T:** Fine-Tuning

**C-W:** Class-Weight

------

# 3) Conclusiones:
- **Rendimiento:**
  - Al aplicar class-weight, la métrica "specificity" aumentó. Lo cual es bueno, ya que el modelo experimentó un mejor performance al predecir la clase minoritaria.
  - Al realizar Fine-Tuning al modelo, se tuvo un mejor performance, lo cual se evidencia en la tabla de comparativa de rendimiento.

------

# 4) Mejoras futuras:
- Aplicar diferentes técnicas de balanceo de clases y comparar las métricas como specificity, accuracy y F1_Score.
- Probar modelos preentrenados diferentes a VGG16 y evaluar performance.
