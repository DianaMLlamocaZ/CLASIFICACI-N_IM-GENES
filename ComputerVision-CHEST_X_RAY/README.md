# Detección de neumonía mediante rayos X de torax
Este proyecto se basa en la detección de neumonía mediante imágenes de rayos X de pacientes sanos frente a los afectados por neumonía.
- Red entrenada con fine-tuning
- Red entrena sin fine-tuning

**Importante:**
* Evaluación de modelos en base a su rendimiento.

**Datos utilizados:**
- Chest X-Ray-Dataset: [https://www.kaggle.com/datasets/praveengovi/coronahack-chest-xraydataset]

-----

# 1) Comparación de modelos : Fine-Tuning vs Feature Extraction

### 1.1) Modelo sin Fine-Tuning, no class weight
El modelo sin fine-tuning se entrenó utilizando el modelo VGG16.

#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)

### 1.2) Modelo sin Fine-Tuning, sí classweight
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad y class weight para el desbalanceo de clases.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)

### 1.3) Modelo no Fine-Tuning, sí classweight, Dropout
#### **Técnicas:** 
- Data augmentation para que el modelo se entrene con más variabilidad y class weight para el desbalanceo de clases.
- 2 capas densas:
  - 1000 neuronas (regularizador L2), 1 neurona (clases a predecir: presencia o no presencia)
- Capa dropout (30%)
- Batch normalization

### 1.4) Modelo no Fine-Tuning, sí classweight, Dropout
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
Aquí se compara la métrica clave para ambos modelos:

| Métrica    |       NO F-T, NO C-W, L2      |     NO F-T, SÍ C-W, L2        |      NO F-T, SÍ C-W, L2, Dropout       |    SÍ F-T, SÍ C-W, L2, Dropout        |
|------------|-------------------------------|-------------------------------|----------------------------------------|---------------------------------------|
|  Accuracy  | 80.12%                        | 84.61%                        | 81.25%                                 | 85.89%                                |
| Specificity| 49.57%                        | 60.25%                        | 50.85%                                 | 64.10%                                |
|  F1_Score  | 86.09%                        | 88.96%                        | 86.89%                                 | 89.76%                                |

**F-T:** Fine-Tuning
**C-W:** Class-Weight
