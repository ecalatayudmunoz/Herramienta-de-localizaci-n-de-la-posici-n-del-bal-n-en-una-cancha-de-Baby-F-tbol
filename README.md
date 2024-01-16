# Readme del Proyecto de Detección Automática de Posición del Balón en Baby Fútbol

## Objetivo del Proyecto

Este proyecto tiene como objetivo desarrollar una herramienta capaz de detectar si el balón se encuentra dentro o fuera del área durante un juego de Baby fútbol. La detección automática de esta posición permitirá a los árbitros tomar decisiones rápidas y precisas sobre la validez de un gol, especialmente cuando la ubicación exacta del balón es difícil de determinar debido a la velocidad del juego.

## Tecnologías Utilizadas

La herramienta se ha desarrollado en Python utilizando las siguientes librerías:

- **OpenCV**: Para el procesamiento de imágenes.
- **Numpy**: Para el manejo de datos.
- **google.colab.patches**: Para utilizar ciertas funciones de OpenCV en Google Colab.
- **math**: Para realizar cálculos matemáticos.
- **tqdm**: Para monitorear la eficiencia de las funciones.
- **torch**: Para implementar YOLOv5.
- **shutil y os**: Para el manejo de archivos.

## Procesamiento de Imágenes

### 1. Toma de Imágenes

Para el correcto funcionamiento del algoritmo, las imágenes deben tomarse siguiendo ciertas pautas, como grabar los videos a la altura de la zona entre las áreas de la cancha, usar un trípode y asegurarse de que en algún frame del video aparezca la cancha sin personas ni objetos.

### 2. División y Reconstrucción del Video

Después de cargar el video, se divide en frames para su procesamiento individual. Una vez completados los procedimientos de tratamiento de imágenes, se reconstruye el video con el mismo ratio de frames por segundo.

### 3. Diferenciación de Zonas en la Cancha

La detección de la línea del área se realiza utilizando algoritmos de resaltado de colores, Canny y la Transformada de Hough Probabilística. Se ajustan los parámetros para filtrar las líneas no deseadas y verificar la predicción de la línea del área.

### 4. Creación de Máscaras de Zonas

Se crean máscaras binarias para el área y el balón, permitiendo una comparación precisa de sus posiciones.

### 5. Detección del Balón

La detección del balón se realiza utilizando el modelo YOLOv5, filtrando objetos de la clase "sports ball" con un umbral de confianza.

### 6. Detección de Intersecciones entre el Balón y las Áreas

Se realiza una operación binaria AND entre las máscaras del área y el balón para determinar si el balón está dentro o fuera del área durante la jugada.

## Uso del Código

Se proporciona un código comentado para implementar los algoritmos mencionados en este documento.

---

Con esta información, los usuarios pueden comprender el propósito del proyecto, las tecnologías utilizadas y los pasos específicos para procesar las imágenes y lograr la detección automática de la posición del balón en el Baby fútbol.
