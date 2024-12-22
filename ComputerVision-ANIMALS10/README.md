# Clasificación de imágenes en el dataset Animals-10 de Kaggle
- Dataset: [Animals-10](https://www.kaggle.com/datasets/alessiocorrado99/animals10/data)
- Modelo usado: VGG16
  
=====

# Transfer Learning: Feature extraction vs Fine Tuning
**Nota:** **"feature extraction"** se refiere a \usar el modelo preentrenado\ para extraer características del nuevo conjunto de datos, \sin modificar los pesos del modelo\. Mientras que **"fine-tuning"** implica entrenar más el modelo, previamente entrenado, en un nuevo conjunto de datos, lo que permite actualizar algunos de sus pesos para adaptarse mejor a la nueva tarea. refers to using a pre-trained model to extract features from new data without modifying the model's weights, while "fine-tuning" implica entrenar más el modelo, previamente entrenado, en un nuevo conjunto de datos, lo que permite actualizar algunos de sus pesos para adaptarse mejor a la nueva tarea. involves further training a pre-trained model on a new dataset, allowing some of its weights to be updated to better suit the new task, making it more adaptable to the specific problem at hand;
Para medir el rendimiento del modelo preentrenado, hice 2 pruebas: el modelo preentrenado solamente para extracción de características y el mismo modelo preentrenado, pero aplicando fine tuning, de tal forma que el modelo preentrenado se adapte al dataset.

=====

# Resultados

## Feature extraction
