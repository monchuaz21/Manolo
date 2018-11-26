
## Introducción a Big Data

La siguiente práctica consiste en analizar una base de datos de votaciones en diferentes distritos electorales para los 5 candidatos que vimos en el ejercicio en clase. Para esto, haremos uso de una máquina virtual para poder entrar a ubuntu y posteriormente a Hadoop y ahí hacer el proecesamiento de datos con un Mapper y un Reducer para poder realizar la práctica.

Comencemos a conectarnos a la máquina virtual asociada a la IP que se nos otorgó en clase:

![image1.png](attachment:image1.png)

Procedemos conectarnos a Hadoop

![image2.png](attachment:image2.png)

Ahora modificaremos el código en python que tenemos en nuestro Mapper para que quede a nivel distrito y le otorgaremos los permisos correspondientes:

![im9.png](attachment:im9.png)


```python
Ahora modificaremos el código en python para nuestro Reducer:
```


      File "<ipython-input-2-3f63656be187>", line 1
        Ahora modificaremos el código en python para nuestro Reducer:
                          ^
    SyntaxError: invalid syntax
    


![im4.png](attachment:im4.png)

Utilizando el comando de hadoop jar para poner como input el archivo de votación y generar nuestra salida "dist1", utilizaremos los códigos en python de EjMapper y EjReducer:

![im10.png](attachment:im10.png)

I.	¿Cuántos distritos electorales contiene el archivo votacion.csv?

Una vez que ejecutamos los comandos de arriba, obtenemos un archivo que se genera dentro de nuestro output "dist1" el cual tiene el nombre de part-00000

![im12.png](attachment:im12.png)

Por lo tanto podemos ver que hay 20 distritos electorales

II.	¿Cuántas encuestas se obtuvieron por distrito electoral? ¿En qué distrito se capturaron más encuestas? ¿En cuál menos?

En el distrito 8425 fue el distrito que más encuestas tuvo, al contar con 10,192. El que menos tuvo fue el distrito 1232 que cuenta con 1,963 encuestas

III. ¿Cuántos votos obtuvo cada candidato en cada distrito electoral? ¿Cuántos obtuvo el candidato 1 en el distrito 1232? ¿Cuántos el candidato 5 en el distrito 9184?


```python

```

IV. ¿Cómo se distribuyó el voto por género para cada candidato en cada distrito electoral? ¿En qué distrito y para qué candidato se obtuvo la menor preferencia electoral de los varones?


```python

```

V.	Calcule el histograma de votación por hora para todo el proceso electoral.


```python

```
