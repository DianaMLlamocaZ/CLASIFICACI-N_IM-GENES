# Clasificación de imágenes en el dataset Animals-10 de Kaggle
- Dataset: [Animals-10](https://www.kaggle.com/datasets/alessiocorrado99/animals10/data)
- Modelo usado: VGG16
  
=====

# Transfer Learning: Feature extraction vs Fine-Tuning

Para medir el rendimiento del modelo preentrenado, hice 2 pruebas: el modelo preentrenado solamente para extracción de características y el mismo modelo preentrenado, pero aplicando fine-tuning, de tal forma que el modelo preentrenado se adapte al dataset.

-----

**Nota:** **"feature extraction"** se refiere a *usar el modelo preentrenado* para extraer características del nuevo conjunto de datos, *sin modificar los pesos del modelo*. Mientras que **"fine-tuning"** implica *entrenar más el modelo*, previamente entrenado, en un nuevo conjunto de datos, lo que *permite actualizar algunos de sus pesos* para adaptarse mejor a la nueva tarea.

=====

# Resultados

## Feature extraction

### Feature extraction - VGG16:

- Métricas del **accuracy** y **loss**:

![](https://github.com/DianaMLlamocaZ/CLASIFICACION_IMAGENES/blob/main/ComputerVision-ANIMALS10/ResultadosMetricas/SFT-1.JPG)

- **Accuracy**: 84.95%

- Gráficas del **accuracy**:

![](https://github.com/DianaMLlamocaZ/CLASIFICACION_IMAGENES/blob/main/ComputerVision-ANIMALS10/ResultadosMetricas/SFT-2.JPG)

- Gráficas del **loss**:

![](https://github.com/DianaMLlamocaZ/CLASIFICACION_IMAGENES/blob/main/ComputerVision-ANIMALS10/ResultadosMetricas/SFT-3.JPG)

-----

### Fine-Tuning - VGG16:
Accuracy: 91.23%

- Métricas del **accuracy** y **loss**:

![]()

- **Accuracy**: 91.23%

- Gráficas del **accuracy**:

![]()

- Gráficas del **loss**:

![]()

-----


