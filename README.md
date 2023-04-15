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

![Texto alternativo](https://ecuacionde.com/wp-content/uploads/2023/02/formula_desviacion_estandar.png)
![Fórmula de la desviación estándar](https://ecuacionde.com/wp-content/uploads/2023/02/formula_desviacion_estandar.png)

