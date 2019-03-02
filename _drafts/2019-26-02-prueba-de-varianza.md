# Prueba de varianza

Otra de las propiedades que debe satisfacer el conjunto $r_i$ es que sus números tengan una varianza de $1/12​$. La prueba que busca determinar lo anterior es la prueba de varianza, establece las siguientes hipótesis.

La prueba de varianza consiste en determinar la varianza de los $n$ números que contiene el conjunto $r_i​$ mediante la ecuación siguiente. 

Después se calculan los limites de aceptación inferior y superior con las siguientes ecuaciones
$$
LI_{v(r)} = \frac{x^2(1-\alpha)/2, n-1}{12(n-1)} \\
LS_{v(r)} = \frac{x^2(1-\alpha)/2, n-1}{12(n-1)}
$$
Si el valor de $v(r)$ se encuentra entre los limites de aceptación decimos que no se puedes rechazar el conjunto $r_i$ tiene una varianza de $1/12$, con un nivel de aceptación de $1-\alpha$ de lo contrario se rechaza el conjunto $r_i$, tiene una varianza de $1/12$. 