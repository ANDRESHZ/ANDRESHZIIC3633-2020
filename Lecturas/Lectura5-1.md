# **Critica: Combining Predictions for Accurate Recommender Systems**

_**Impresión del Paper:**_ 

> el paper genera gran expectativa respecto a la implementación de diferentes métodos y formas de atacar el problema de recomendación, la profundidad con la cual apunta a los temas es pequeña, pero debido a bagaje previo se torna perfecta para el entendimiento. Al final el cambio no fue monumental pese a todo lo que debió requerir a los investigadores realizarlo. El contenido se desenvuelve muy bien, es preciso con la información. Falta desde mi percepción personal, un poco de profundidad en la explicación de los métodos de bagging implementados, Finalmente se nota un gran despliegue de resultados y mediciones de los 18 métodos usados como base.

```[Agrupación de métodos mayor rendimiento: ¿La unión hace la fuerza? (mejoras en el RMSE) o ¿El fin justifica los medios? (uso de gran cantidad de recursos)].```

El articulo hace una gran recopilación de la información usada por **18 métodos** (_**KNN, SVD, AFM…**_) en distintas variaciones, lo cual brinda un gran bagaje y la obtención los métodos que abordan en diferentes maneras, centrándose en la métrica de ![RMSE](https://latex.codecogs.com/gif.latex?RMSE%3D%5Csqrt%7B%5Cfrac%7B1%7D%7BN%7D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%5Cleft%20%28%5COmega%20%28x_i%29-y_i%20%5Cright%20%29%5E2%7D) **como objetivo de la investigación**.

Haciendo uso de e**nsamblaje de diferentes método**s como precepto pretenden mejorar la métrica en relación, esto es aplicado sobre el ampliamente conocido dataset del _Netflix Prize_, conglomeración de 10^8 ratings capturados por 7 años, el uso de **este dataset es de gran ayuda** para la investigación debido a que sido **usado ampliamente a nivel académico y comercial** (_lo cual ha generado varias aplicaciones sobre el mismo, como las 18 seleccionadas_).

La hipótesis central es agrupar métodos que **resuelven el problema de diferentes maneras**, a fin de dar valores agregados entre si (_lo cual abre una gran expectativa respecto a los resultados esperados_), pese a que al final los resultados un cambio en algunas centésimas (**igual la investigación abre un campo gigantesco, y el esfuerzo de implementación debió ser de igual proporción**), pese a eso el análisis de tiempo de entrenamiento abre la duda siendo ![OperTiempo](https://latex.codecogs.com/gif.latex?O%28M%5Ccdot%20U%5E2%29) la más alta, y al enfrentarse a **esta arquitectura planteaba el reto a vencer** (_pues se debieron encontrar la manera de entrenar de manera óptima_).

Actividades como la **subdivisión** del dataset, la **distribución de información** son aplicadas usualmente, al igual que en presente artículo, **bleding** (_combinación lineal_); lo que destaca son los métodos de **bagging  y boost** posteriormente usados, lo cuales centran sus esfuerzos en **reducir tiempo ademas de optimizar el entrenamiento y generación de ratings** (_o recomendaciones_), mientras **bagging busca subdividir** el problema dejandolo mejor estructurado y más rápido de resolver, **boost aplica el entrenamiento en cadena** de árboles de decisión (_las dos en conjunto aumentan la precisión de los árboles de decisión_).

La selección de los parámetros de cada elemento debería pasar por una **etapa de optimización para los elementos a ser unidos** (_para el actual trabajo estos, ya estaban expuestos en los métodos escogidos_), posteriormente la naturaleza distinta de los métodos y sus divergencias debían ser controladas, de allí implementar una **retroalimentación y comparación cruzada de las salidas** en el entrenamiento fue lo que ayudo a la convergencia del método (_adicional a métodos de limitación, como limita **K** hojas los árboles y datos de entrada reducidos_).

La arquitectura permitió asi, **paralelizar el entrenamiento** de redes neuronales y la convergencia dividida en múltiples partes, para evitar un arranque frio se **entrega un subespacio de características** de los elementos de forma aleatoria (_probelmas de repetibilidad se podrina presentar_), así aumentar la velocidad y precisión de arranque. Al final la obtención de un método que intercambia el promedio de **aprendizaje ensamblado y las bondades de los métodos Base**.

La sección de resultados esta muy bien documentada y explicada, lo cual es muy bueno, pero se debe a la necesidad de los investigadores de resaltar su resultado (_pues la diferencia no fue tan grande, como supongo esperaban_)


**Trabajo a Futuro:** `Algo que me dejo desconcertado es el modo de selección y subdivisión de los datasets de entrenamiento, pues tomaban como medida a poblaciones con un límite mínimo de actividad y número de interacciones, lo cual produciría un posible **sesgo hacia los usuarios activos**, usar una _**arquitectura paralela para personas con actividad media**_ podría mejorar las métricas.`

* > **PD**: Los cambios son muy pequeños y hay secciones en las que la selección se realizó aleatoriamente, tanto de datos como de parámetros, lo cual deja mucho que pensar respecto a la **repetibilidad de los resultados obtenidos**.
