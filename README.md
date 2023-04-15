# Regresion Logistica

Al igual que un Árbold de Decisión, es un modelo de clasificación. ¿Qué lo diferencia de una regresión lineal simple o múltiple?
Se utilizan para predecir valores continuos, la regresión logística se utiliza para predecir la probabilidad de que un evento ocurra o no, la variable de salida es una variable binaria (1 o 0, verdadero o falso).
En otras palabras, la regresión logística no predice el valor numérico de la variable de salida, sino que predice la probabilidad de que la variable de salida sea verdadera o falsa, en función de las variables de entrada. Por lo tanto, la regresión logística se utiliza para clasificar datos en dos o más clases.

Si al momento de guardar tu clase en una variable, algo como:
```sh
logreg = LogisticRegression()
```
Sale un error de máximo de iteraciones, Puedes pasarle un parámetro de max_iter, 

```sh
logreg = LogisticRegression(max_iter=10000)
```
