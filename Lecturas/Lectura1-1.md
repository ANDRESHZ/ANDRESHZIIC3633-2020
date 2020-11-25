**Critica: Item-Based Collaborative Filtering Recommendation Algorithms**

_**Impresion del Paper:**_ 

> Un gran articulo resume perfectamente le uso de algoritmos de filtrado colaborativo dando una gran entrada a los basados en usuario, con una claridad amplia. Y posteriormente muestra a detalle el uso de los basados en ítem, ofreciendo un análisis matemático profundo, ejemplos y métricas de los resultados obtenidos.

El articulo pone muestra bajo la sección 2 una gran comparación y un contexto claro del uso del modelo por Ítem, esto presentándolo con los “*problemas*” presentados por los basados en usuario (Precisión, Escalabilidad y efectos de vecindades).

El fuerte del articulo a partir de la sección 3 se aprecia el cambio y ajuste bases matemáticas de similaridades ( ![Similar](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Clarge%20sim%28i%2Cj%29) ) basadas en el nuevo precepto (ítems), presentando el uso de similaridades de coseno y Pearson, al igual que otras como las de predicción ( ![Pred](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Clarge%20P_%28u%2Cj%29) ) y una regresión ( ![Regr](https://latex.codecogs.com/gif.latex?%5Cdpi%7B120%7D%20%5Clarge%20%5Cbar%7BR%7D%27_N) ) mostrando un modelo básico (pero efectivo) para aproximación.

Se aprecia la inclusión de vecindades, para el uso de similaridades y la reducción de computo para cierta cantidad de **items =k**. Lo cual ayuda tanto a la predicción pues las distancias o diferencias no serán tan altas y permite hace cálculos previos en pequeños grupos.

Una cuestión que me deja un tanto apagado es el uso de un solo Data set (que para efectos de medición va muy bien), a nivel académico deja un vacio respecto al uso de distintos ambientes de aplicación y sus efectos, al igual que características que cambian con los diferentes tiempos de sets debido a su naturaleza de aplicación. Pero para efectos del objetivo instado en el titulo del articulo esto basta y sobra.

La mediciones de Errores al usar meretricias de Media de valor absoluto elimina la posibilidad de reconocer la *varianza y correlación de las respuestas*. Se pudo implementar medidas  en diferentes intervalos de aceptación, e incluso la introducción de basura en datasets (datos de baja correlación) a modo de ruido para ver su respuesta.

Al momento de realizar las métricas datos necesarios que podrían ser importantes como Sistema operativo, Caches, numero de Hilos, Buses de trasmisión, ocupación previa de recursos ambientes de pruebas..., podrían ser datos relevantes para buscar métodos para futuras o**ptimizaciones de código y velocidades de ejecución**.

Se evidencia un espacio respecto al pre-calculo dinámico de matrices, basadas en las mismas similaridades, evitando así el calculo completo por la inclusión de un nuevo ítem o rating al mismo, esto permitiría realizar **cálculos Online mas rápidos** par obtener mejores prestación en tiempos de salidas, y dando espacio a calcular en instantes de tiempo libres.