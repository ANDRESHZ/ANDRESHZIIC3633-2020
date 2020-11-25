# **Critica: Collaborative Filtering for Implicit Feedback Datasets**

_**Impresión del Paper:**_ 

> El articulo inicia con gran fuerza presentando de manera clara las características usadas para el modelo basado en retroalimentaciones de usuario implícitas, y realiza una buena caracterización de las mismas brindando un contraste con las demás indicadas en el cuerpo del documento (Retroalimentación Explicita), pero desde mi posición se vuelve bastante tosco para el lector al ahondar en temáticas de manera generalizada en los apartados posteriores. Los resultados me dejan un hueco respecto a los métodos de comparación y evaluación (no frente a su explicación) en el estándar de comparación dando la apariencia del uso de un método que los favoreciera mayoritariamente a ellos; Por ultimo se destaca que la información presentada como resultados es un tanto sesgada a su trabajo por lo indicado.

```[Aclaro que es cuestión de mi percepción```, **implícita** ```asi como el tema del articulo].```

Respecto las secciones implementadas, me parece muy bueno pues presenta de manera muy adecuada la introducción del método y las razones que condujeron a su implementación, ademas de que se ve la  ayuda y participación de los diferentes métodos de recomendación.

Entrando en materia, la metodología usada deja claro que una vinculación de modelos de retroalimentación explicita e implícita en el sistema de recomendación, dejándolo abierto a su uso (_pese a no ser indicado directamente en la discusión_), pero en el uso de practicas del SVD si se evidencia la inclusión de preceptos en su modelo.

Presenta una **buena solución** para usuarios pasivos de los sistemas, pues se basa en el comportamiento del mismo sobre el sistema, esta presunción demuestra su aserción (_dando una solución a la dispersión de datos en ratings del modelo explicito_), la dificultad de esta solución radicaría en la definición adecuada de esas características implícitas al igual que de sus rangos tanto a la relevancia y efecto sobre la salida se refiere.

Por otra parte una característica remarcarle del método es arrancar en frio, sea para ítems o “_usuarios_” nuevos, A usuarios nuevos características iniciales de **Usabilidad** serian la entrada de allí el por que de las “_comillas_”, pues igual necesita la interacción básica del usuario con el sistema; por otro lado con ítems nuevos genera una mayor cercanía y facilidad pues hay información relevante en el sistema de ítems anteriores correlacionados (Canales, ratings, tiempos….).

El **ruido inherente** a este modelo es alto, debido a que son características no visibles a simple vista y que se pueden ver afectadas por comportamientos aislados, como el _mal uso de la plataforma, la probabilidad de estar interesado o solo ausente sobre el sistema_.

Un tema de estudio muy relevante se vislumbra, pero no se toca a profundidad es respecto a las **explicaciónes de la recomendación al usuario y el uso de la confidencia** ademas de su efecto sobre otros usuarios similares

El apartado de complejidad computacional me pareció un poco sobre valorado respecto a que no hubo resultados y comparación. (_lo cual hizo que la lectura se tornara un tanto aburrida_), pese a ser supremamente importante para **dimensionar la complejidad del problema y su posterior aplicabilidad**.

Por ultimo la comparación usada por los autores indican un **sesgo** por ayudar a su método, pues no usan un estándar (_entendible frente a que es un método implícito_), pero los gráficos y resultados en pruebas enunciadas, si demostraron la inclinación (_el uso de factores unicamente, y no dar oportunidad con diferentes vecindades por ejemplo_), evidenciable en la grafica 1 siendo muy poco diciente, **los resultados destacables fueron exiguamente comparables** dejándome con la idea, de ```
¿si sera un gran método?``` Pero aclaro que si es un enorme cambio de paradigma y puerta de entrada a este tipo de algoritmos (tal vez me ocurrió al leer lo del dicho, quedándome en: **mejor el malo conocido que el bueno por conocer**).

* > **PD**: la hibridación entre los sistemas explícitos e implícitos es una adecuada a modo de discusión, donde podríamos mejorar estos algoritmos implícitos con la participación de información explicita, lo cual abré un marco de menor dispersión probabilística en las salidas.