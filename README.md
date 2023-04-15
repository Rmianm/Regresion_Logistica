# Regresion Logistica

Al igual que un Árbold de Decisión, es un modelo de clasificación. ¿Qué lo diferencia de una regresión lineal simple o múltiple?
Se utilizan para predecir valores continuos, la regresión logística se utiliza para predecir la probabilidad de que un evento ocurra o no, la variable de salida es una variable binaria (1 o 0, verdadero o falso).
En otras palabras, la regresión logística no predice el valor numérico de la variable de salida, sino que predice la probabilidad de que la variable de salida sea verdadera o falsa, en función de las variables de entrada. Por lo tanto, la regresión logística se utiliza para clasificar datos en dos o más clases.

Si al momento de guardar tu clase en una variable, algo como:
```sh
logreg = LogisticRegression()
```
sale un error que dice " ConvergenceWarning: lbfgs failed to converge ", Esto puede deberse a varios motivos, como el hecho de que el modelo no sea adecuado para los datos, la falta de normalización de los datos, el número insuficiente de iteraciones, la falta de regularización, entre otros, en el mejor de los casos te dirá que simplemente aumentes el número de iteraciones por lo que vas a colocar lo siguiente,

```sh
logreg = LogisticRegression(max_iter=10000)
```
En el caso del archivo de Diabetes, las variables tienen rangos diferentes unas de las otras por eso sería conveniente hacer una estandarización o normalización de los datos.
Demos un repaso a la estandarización o normalización. son técnicas utilizadas en el procesamiento de datos para transformar las variables en un rango común y facilitar su comparación y análisis.
¿Qué diferencia una de la otra?, radica en el proceso de transformación de los datos.

***Normalización***
La normalización implica escalar los datos para que estén en un rango específico, generalmente entre 0 y 1. Esto se hace dividiendo cada valor por el valor máximo en la variable. Es útil cuando se desea comparar las magnitudes relativas de diferentes variables que tienen diferentes unidades o escalas. Ejemplo de técnicas de normalización son la escala mínima-máxima, Veamos un ejemplo desde el punto de vista matemático.

Supongamos que tenemos los siguientes datos de edad:
```sh
[18, 22, 25, 30, 40, 50, 60, 70, 80, 90]
```
Ahora podemos seguir los siguientes pasos, 

1. Encontrar el valor mínimo y máximo de la variable. En este caso, el valor mínimo es 18 y el valor máximo es 90.
2. Restar el valor mínimo de cada valor en la variable. Esto asegura que el valor mínimo sea ahora 0.

```sh
[0, 4, 7, 12, 22, 32, 42, 52, 62, 72]
```
3. Dividir cada dato por el valor máximo.

```sh
[0.00, 0.06, 0.10, 0.17, 0.31, 0.44, 0.58, 0.72, 0.86, 1.00]
```
Ahora, los datos de edad están normalizados en un rango de 0 a 1, lo que permite comparar las magnitudes relativas de diferentes variables que tienen diferentes unidades o escalas.


<img src="https://ecuacionde.com/wp-content/uploads/2023/02/formula_desviacion_estandar.png" alt="Texto alternativo" width="180" height="100"> <img src="https://www.sage.com/es-es/blog/wp-content/uploads/sites/8/2021/07/Varianza_1.jpg" alt="Texto alternativo" width="280" height="120">
