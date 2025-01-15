# Segmentación de imágenes, usando una red neuronal convolucional encoder-decoder desde cero
Este proyecto se basa en la segmentación de imágenes, usando el dataset **The Oxford-IIIT Pet Dataset**, con el objetivo de entrenar una red que aprenda a segmentar el background, de los objetos presentes en la imagen.

**Datos utilizados**
- The Oxford-IIIT Pet Dataset: []

----------

# Modelo:

#### **Técnicas:** 

#### Encoder:
  - 6 capas convolucionales 2D
  - Implementación de 'padding' y 'strides' en las capas (para una extracción de características más precisa y por la importancia del *spatial location* en segmentación de imágenes, respectivamente)

#### Decoder:
  - 6 capas convolucionales 2D transpose (por el upsampling del espacio de características, pues el size del output debe ser igual al size del input)
  - Output: Conv2D layer con el número de filtros equivalentes al número de clases tomadas en cuenta para la segmentación en el conjunto de datos.

---------

# Métrica - Gráfico de desempeño
A continuación, muestro la gráfica de la métrica *loss* durante el entrenamiento (training vs validation loss):

![TrainingValidation_Loss](https://github.com/DianaMLlamocaZ/SEGMENTACION_IMAGENES/blob/main/ComputerVision-OXFORD_PETS/Imagenes-Metrica/Loss.JPG)

---------

# Imagen de prueba:
Aquí presento una imagen, para la cual utilizaré el modelo para predecir una máscara:

- Imagen de prueba:
  ![ImagenDePrueba](https://github.com/DianaMLlamocaZ/SEGMENTACION_IMAGENES/blob/main/ComputerVision-OXFORD_PETS/Imagenes-Metrica/Prueba1.JPG)

- Máscara predicha por el modelo:
  ![MáscaraPredicha](https://github.com/DianaMLlamocaZ/SEGMENTACION_IMAGENES/blob/main/ComputerVision-OXFORD_PETS/Imagenes-Metrica/Prueba2.JPG)
