# **Critica: Deep Learning based Recommender System: A Survey and New Perspectives (from 1 to 3.4)**

_**Impresión del Paper (Personal):**_ 

>Una extensa revisión de sistemas recomendadores, se centra en la aplicación cualitativa y teórica de las diferentes técnicas, es una descripción desde mi punto de vista muy centrada en público intermedio, y sirve como base para definir el estado del arte hasta la fecha de estudio en el uso de Deep Learning en Sistemas recomendadores (o en algunas de sus fases), además definen adecuadamente con cierto nivel de profundidad matemática (suficiente para entender y posteriormente investigar y aplicar). De pronto la extensión se hubiera podido reducir en las partes introductorias y explicaciones repetitivas.

```[Deep learning - estado del arte en recomendación: (buena subdivisión del estudio) Como dijo el carnicero vamos por partes].```


Desde un punto de vista de conocimiento el apartado de introducción es **extenso y soso** pues su extensión es alta respecto a la baja densidad información que entrega (_larga y vacía_). Igual es necesaria para la **contextualización del lector** (_pese a poder ser sintetizable_). Se define entonces que el Deep Learning tiene una alta capacidad de **captura de características y relaciones de múltiples naturalezas** (_como lo ha venido expresando en auge y aplicabilidad_).

Su contenido la convierte en una **Guía y revisión completa de redes neuronales y aprendizaje** aplicado a recomendación (_Como sistema, modelo o participante del proceso_), se tomó en cuenta que se realizará una optimización con Gradiente conjugado estocástico (_SGD_), con un modelo de clasificación de papers, obteniendo métodos como **perceptrón multicapa** (_MLP_), **Redes Convolucionales** (_CNN_), **Redes Recurrentes** (_RNN_), **Redes adversarias** (_AN_)… así pues es definible que las redes neuronales **aprovechan los sesgos y repetibilidad de información** (_puede llegar a incluir secuencias o memorias_) y como conocemos, gracias a su arquitectura el **uso de GPU es viable** (_hace viable su entrenamiento y aplicación_).

Los autores muestran como estas redes aprovechan características de **no linealidad, obtención de representaciones** (_embeddings_), **modelamiento de secuencias de datos** (_voz, texto, chats, imágenes…_) …; Flexibilidad respecto a la cantidad de **frameworks** (_Tensorflow, Pytorch, caffe, Keras, etc_) disponibles, además de tender a realizarse por **módulos o bloques**, lo cuales brindan capacidad de unión y mezcla (_Múltiples variantes y conceptos mixtos_). En el otro extremo se observa que debido a ser modelos de **caja negra** no se puede acceder o conocer datos intermedios (_pérdida de conocimiento y evaluación_), depende de la información de aprendizaje y **alto consumo de información** (_entrenamiento, grandes cantidades de datos, que expresen la totalidad de las posibilidades y sea lo suficiente para denotar los cambios_), **Optimización de hiperparametros** (_suele ser en parte heurística_), finalmente evitar el **sobre entrenamiento** (_perdiendo flexibilidad o características blandas / generales_).

El estudio de estado del arte se muestran **209 referencias** (_no todas de DeepLearning_), relacionadas a características se identifican las de la **tabla 1**, con 23 MLP, 26 Autoencoder, 25 CNN, 28 RNN, 7 Restricted Boltzmann Machine (_RBM_), 4 AN… para un **total de 149 Referencias categorizadas** (_algunas referencias  contenían múltiples métodos_). Identifican ventajas individuales por ejemplo MLP es capaz de **describir interacciones no lineales entre Usuarios e Items**, o las CNN **representaciones tanto locales como globales** de información o **relaciones heterogéneas**.

Debido a la extensión del documento centrare la atención en los métodos que me parecen interesantes por ejemplo MLP que usa para el **Neural Collaborative Filtering** con cálculo de Rating ![RATINGMLP](https://latex.codecogs.com/gif.latex?%5Chat%7Br%7D_%7Bui%7D%3Df%28U%5ET%5Ccdot%20s%5E%7Buser%7D_u%2CV%5ET%5Ccdot%20s%5E%7Bitem%7D_i%7CU%2CV%2C%5Ctheta%20%29) donde se puede encontrar **la mezcla de parte lineal**  en la Factorización matricial (_MF_) y la **descripción no lineal** del MLP. (_siendo **S** la información de usuarios e items_), usando los factores latentes _U_ y _V_ (_EJ: Recomendación 2 etapas Youtube generación y clasificación de candidatos_).

Las **recomendaciones basadas en codificador**, pueden obtener representaciones de características (_en su zona de cuello de botella con menor dimensionalidad_) y completar las matrices de interacciones o datos en la **fase de reconstrucción,** ejemplo de ello es el **filtrado colaborativo con codificador automático** toma factores latentes _r(u)_ y _r(i)_  de forma parcial para reconstruirlos a la salida dada por la función objetivo  ![IAUTOREC](https://latex.codecogs.com/gif.latex?%5Carg%5Cmin_%7B%5Ctheta%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%20%5C%7C%20r%5E%7B%28i%29%7D-h%28r%5E%7B%28i%29%7D%3B%5Ctheta%29%20%5Cright%20%5C%7C%5E2_O%20&plus;%5Clambda%5Ccdot%20reg)  y se maneja un _h_ definido por funciones de activación (_f()_ y _g()_), parámetros de la red _θ_ y factores latentes _V_ (_además de ajustes dados por  μ  y b_), la norma ||  ||O **solo considera ratings de los elementos observados**.

Por ultimo las **recomendaciones con CNN**, muestra ejemplo de basarse y aprovechar el **Punto de interés** (_POI_), permitiendo **extrapolar información de tipo visual** (estas redes son muy usadas en procesamiento de imágenes, por versatilidad y practicidad) y los **factores latentes de los usuarios**. El **Visual BPR** para la obtención de parches de las imágenes y usarla en dentro de la MF tanto para **mejorar la velocidad como en ajuste de valores**. Otro modelo explicado es el **DeepCoNN** permite extracción de texto y modelar a los usuarios (_aprovechamiento de la reducción de dimensionalidad_), conectando las salidas de redes _Xi_ (_items_) y _Xu_ (_usuarios_) a una **capa de predicción y/o reconstrucción** (_también aplica factorización matricial_), mostrando su posibilidad de uso en tareas de **autocompletar o manejo de audios y videos** (_uso de múltiples capas y múltiples tiempos_).

* > **PD**: La lectura es **bastante extensa**, pese a ser una temática muy entretenida es bastante **difícil de digerir**, pero si se realiza para **obtener bagaje y conocimiento superficial** es excelente (_además de ser un gran estado del arte_) de allí la frase de inicial, es importante **solo tomar las partes que nos servirán o nos son más interesantes** (_concepto ambiguo del lector_).