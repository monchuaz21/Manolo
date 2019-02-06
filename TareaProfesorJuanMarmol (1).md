
**Equipo:**

*Daniel Luizet Castro,
Patricia Trujillo Barrios,
Manuel Jesús Zamora Monroy*

# Redes Neuronales

El siguiente trabajo es sobre un simulador de un problema de clasifiación binario que se encuentra en Playgroud [https://playground.tensorflow.org] en tensorflow en donde a manera visual se puede entender lo que cada parámetro en una red neuronal afecta a la estimación de cada categoría. Para fines del trabajo, el problema que se eligió es el siguiente:

* Dataset : Circle
* Función de activación: Sigmoide
* Split en Train y Test: 50%-50%
* Problema: Clasifiación

Veremos cómo afecta el Learning Rate, el cual afecta el tamaño del "paso" en el gradiente para encontrar un mínimo/máximo local, el número de capas ocultas y la cantidad de features que serán input para el modelo (considerando sólo 2 variables de entrada (x1, x2) y transformaciones a partir de éstas, veremos cómo afecta a la red).

### LR: 0.03; Features: 2; Capas: 2

![Parte1.png](attachment:Parte1.png)

Con estos parámetros, vemos que se logra estimar correctamente cada una de las categorías, utilizando como input las variables "brutas" sin transformación alguna. El error es cercano a 0 y se ve cómo en la segunda capa se "limitan" los bordes azules que forman la figura aunque queda como forma triangular.

### LR: 0.03; Features: 7; Capas: 2

![Parte2.jpg](attachment:Parte2.jpg)

Aquí se incluyeron transformaciones de las variables x1, x2, tales como elevar al cuadrado, su interación (producto) y funciones trigonométricas (seno(x)). Podemos ver que se logra una forma circular de manera casi perfecta. El error es casi 0 y se ve cómo en la segunda capa se limitan los bordes de los círculos. Itera rápidamente.

### LR: 0.03; Features: 2; Capas: 2 (1 con 6 neuronas y la última con 4 neuronas)

![Parte3.jpg](attachment:Parte3.jpg)

Al igual que el primer ejemplo, se llega a una forma triangular, empleando las variables "brutas" sin transformación alguna, y aunque se agreguen neuronas a las capas, no se logra la forma circular, aunque el error sea casi 0.

### LR: 0.03; Features: 2; Capas: 3 (1 con 6 neuronas, otra con 4 y la última con 2 neuronas)

![Parte4.jpg](attachment:Parte4.jpg)

Podemos ver que aunque se agregue una tercera capa, la forma circular final no es "perfecta", aunque el error se aproxime a 0.

### LR: 0.03; Features: 7; Capas: 3 (1 con 6 neuronas, otra con 4 y la última con 2 neuronas)

![Parte5.jpg](attachment:Parte5.jpg)

En contraste al ejemplo anterior, agregando transformaciones de las variables x1, x2 podemos ver que llegamos a un círculo casi perfecto, de tal manera que el error se minimiza y se itera rápidamente.

### LR: 0.03; Features: 2; Capas: 3 (1 con 6 neuronas, otra con 4 y la última con 4 neuronas)

![Parte6.jpg](attachment:Parte6.jpg)

Si eliminamos las transformaciones y agregamos más neuronas, no se llega a la forma circular que obtuvimos en el caso anterior.

### LR: 0.1; Features: 2; Capas: 2

![Parte7.jpg](attachment:Parte7.jpg)

Aumentando el Learning Rate a 10% y dejando sólo las variables brutas, se llega rápidamente a una correcta clasificación, aunque la forma no sea circular perfecta. El paso que se da en el gradiente (ahora de 0.1) hace que encuentre muy rápido los máximos y mínimos locales.

### LR: 0.1; Features: 7; Capas: 2

![Parte8.jpg](attachment:Parte8.jpg)

Del caso anterior, si agregamos más features, vemos que se llega a una forma circular y de manera rápida.

### LR: 0.1; Features: 7; Capas: 3 (1 con 6 neuronas, otra con 4 y otra con 2)

![Parte9.jpg](attachment:Parte9.jpg)

Agregando más capas y con más neuronas, se llega a una clasifiación muy buena con la forma que queremos y no es tardado dado que el paso que se da en el gradiente es de 0.1 (learning rate) y se ve que se encuentran los máximos y mínimos rápidamente.

### LR: 0.1; Features: 7; Capas: 3 (1 con 6 neuronas, otra con 4 y otra con 4)

![Parte10.jpg](attachment:Parte10.jpg)

En este ejemplo agregamos más neuronas a la última capa e igualmente obtuvimos una forma circular casi perfecta, no tarda en lograr esa clasificación y se utilizan todos los features.

### LR: 0.001; Features: 2; Capas: 2

![Parte11.jpg](attachment:Parte11.jpg)

En este ejemplo, reducimos el tamaño del paso que se da en el gradiente a 0.001 para encontrar un máximo o mínimo local ("pasitos") y tarda demasiado en lograr una clasificación. Y como sólo usamos las variables brutas, no se llega a la forma circular.

### LR: 0.001; Features: 7; Capas: 2

![Parte12.jpg](attachment:Parte12.jpg)

Vemos que tomando todos los features, llegamos a la forma circular aunque la clasificación tarda demasiado tiempo, debido a los pequeños pasos que se da en el gradiente.

### LR: 0.001; Features: 7; Capas: 3 (1 con 6 neuronas, otra con 4 y otra con 2)

![Parte13.jpg](attachment:Parte13.jpg)

Se logra una forma circular, se agregan capas y se tarda mucho tiempo en poder lograr una correcta clasificación.

### Conclusión

De las diferentes iteraciones que se hicieron en este ejercicio de clasificación, usando el dataset "circular" y bajo un sampling de 50%-50% entre Train y Test, podemos concluir lo siguiente:

* Si sólo usamos las variables "brutas" (sin transformaciones), no se logra la forma circular "perfecta" y se obtiene algo similar a un triángulo aunque el error sea casi 0.
* Agregando transformaciones de las variables se llega a una forma circular casi "perfecta" y la clasificación sea muy buena y el error casi 0.
* El Learning Rate, si lo aumentamos a 0.1 se logra una clasificación muy rápida, en cualquiera de los escenarios (variando capas, incluyendo features, agregando neuronas).
* Si disminuimos el Learning Rate a 0.001, se tarda demasiado tiempo en lograr una clasificación, en cualquiera de los escenarios.

De esta forma, podemos ver cómo influye el Learning Rate en el gradiente, debido al tamaño del paso que se da hacia cierta dirección para poder encontrar un máximo o mínimo local de la función.

El número de variables que se usan como input influye en la clasifiación, pero agregando transformaciones de éstas, la clasificación es mejor.

# Aplicación de lo visto en clase en el trabajo

Independientemente de las Redes Neuronales, hay un tema de los vistos en el módulo de ML con Python que nos es de mucha utilidad.

Cuando presentamos un modelo y el resultado final a "negocio", siempre nos hacen la pregunta ¿Qué variable es la que influye en el cliente?. Como hemos empleado modelos de Machine Learning, la respuesta siempre es difícil, pues es una interacción de decenas de variables para poder identificar a aquellos clientes con potencial a "algo", ya sea que se vuelvan clientes de "alto valor", con "alta probabilidad de attrition", que el "attrition" sea "silencioso" (es decir, dejan de usar un producto, mas no cancelan el producto).

Ejemplo: Cuando un cliente baja su facturación pero no cancela la tarjeta

Pregunta: ¿Por qué? ¿Es la línea de crédito? ¿Es la tasa?

Con lo que vimos en clase, el paquete ICE nos puede ayudar a responder esa pregunta. Podemos ver las Partial Dependence Plots de cada variable y de cómo a diferentes valores se ve afectada la población, de tal manera que podemos ver cuál es la variable que, por caso, es la que más afecta a cierto cliente. Gráficamente sería difícil de apreciar (a diferencia de lo visto en clase) dado que son ~5 millones de tarjetahabientes, pero podemos utilizar un localizador para que ubique cuáles clientes sí son sensibles a cada una de las variables.

Ejemplo: En riesgo de originación

Pregunta: ¿Por qué aceptas o rechazas una tarjeta a un cliente?

Con lo que vimos en LIME podemos hacer un análisis por caso para ver qué variable fue la que más influyó en el proceso de dictaminación de otorgar o no una tarjeta a un cliente. De esta forma se le puede explicar al cliente (si lo solicita) la razón de rechazo o de aceptación.
