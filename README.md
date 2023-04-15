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
Ahora bien, si quieres implementarlo en código puedes utilizar las siguientes líneas, haz esta transofrmación de datos antes de entrenar el modelo.

```sh
from sklearn.preprocessing import MinMaxScaler
scaler = MinMaxScaler()
normalized_data = scaler.fit_transform(data)
```
Data se refiere a las variables de predicción que ya han sido seleccionadas con anterioridad.

***Estandarización***

Esta técnica implica un procedimiento más detalladom, matemáticamente implica transformar los datos para que tengan una media de cero y una desviación estándar de uno. Esto significa que los datos se centran alrededor de cero y están escalados para que tengan la misma varianza.

Supongamos que tenemos los siguientes datos de ingreso anual:

```sh
[20000, 25000, 30000, 40000, 50000, 60000, 70000, 80000, 90000, 100000]
```

1. Calcular la media y la desviación estándar de la variable, por si no lo recueras aquí te dejo las fórmula de la desviación estandar y la varianza.

<img src="https://ecuacionde.com/wp-content/uploads/2023/02/formula_desviacion_estandar.png" alt="Texto alternativo" width="180" height="100"> <img src="https://www.sage.com/es-es/blog/wp-content/uploads/sites/8/2021/07/Varianza_1.jpg" alt="Texto alternativo" width="290" height="120">

En este caso, la media es 55000 y la desviación estándar es 24018.97.

2. Restar la media de cada valor en la variable. Esto asegura que los datos estén centrados en cero.

```sh
[-35000, -30000, -25000, -15000, -5000, 5000, 15000, 25000, 35000, 45000]
```

3. Dividir cada valor por la desviación estándar. Esto asegura que los datos tengan una varianza de uno.

```sh
[-1.46, -1.25, -1.04, -0.63, -0.21, 0.21, 0.63, 1.04, 1.46, 1.88]
```
Ahora, los datos de ingreso anual están estandarizados, lo que significa que tienen una media de cero y una desviación estándar de uno, nota que al tener una desviación estandar de 1, me garantiza que la varianza también esté cercana a 1, una desviación de 1 me quiere decir que la dispersión de los datos es baja, por ende los datos no están muy alejados de la media

Viéndolo ya desde código podría ser así:

```sh
from sklearn.preprocessing import StandardScaler 
escalar = StandardScaler() 
Estandar_data = escalar.fit_transform(data)
```

***Matriz de Confusión***

A muchos nos confunde una matriz de confusión, así que presta atención.

Supongamos que tenemos la siguiente matriz, que de hecho sale en uno de los ejercicios de Pacientes que he subido.
| Matriz de confusión|
    | 98 | 9 [PlDb] |
    | 18 | 29 [PlDb]|


01, 01

| ------ | ------ |
| 98 | 9 |
| 18 | 29 |

---
Cualquier inquietud no dudes en contactarme a la siguiente dirección miramirezma@unal.edu.co ✌️


