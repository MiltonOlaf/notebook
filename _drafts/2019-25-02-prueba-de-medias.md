# Prueba de medias

Una de las propiedades que deben cumplir los números del conjunto $r_i$ es que el valor esperado sea igual $0.5​$. La prueba que busca determinar lo anterior es la llamada prueba de medias en la cual se plantean las siguientes hipótesis.
$$
H_0:\mu_{r_i} = 0.5 \\
H_1:\mu_{r_i} \neq 0.5
$$
La prueba de medias consiste en determinar el promedio de los $n$ números que contiene $r_i$ mediante la siguiente ecuación:
$$
r = \frac{1}{n} \sum_i^n r_i
$$

$$
LI_r = \frac{1}{2}-Z_{\alpha/2} \left(\frac{1}{\sqrt{12}}\right) \\
LS_r = \frac{1}{2}-Z_{\alpha/2} \left(\frac{1}{\sqrt{12}}\right)
$$

En caso contrario se rechaza que el conjunto $r_i$ tiene un valor esperado $0.5$.

Para el calculo de los limites de aceptación se utiliza el estadístico $Z_{\alpha/2}$ el cual se determina por medio de tabla de distribución estándar.

Como el valor promedio es igual a $0.43250$ se encuentra entre los limites de aceptación, se concluye que no se puede rechazar el conjunto de $40$ números $r_i$, tiene un  valor esperado de $0.5$ con un valor de aceptación $95$