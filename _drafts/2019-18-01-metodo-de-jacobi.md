# Método de Jacobi

Sea un sistema de ecuaciones
$$
\left\lbrace A \right\rbrace\left\lbrace X \right\rbrace = \left\lbrace B\right\rbrace
$$
Si los elementos de la diagonal no son todos cero, se resuelven las ecuaciones como sigue:

**Para un sistema $3*3$**
$$
\begin{matrix}
a_{11}x_1 & a_{12}x_2 & a_{13}x_3 & = b_1 \\
a_{11}x_1 & a_{12}x_2 & a_{13}x_3 & = b_2 \\
a_{11}x_1 & a_{12}x_2 & a_{13}x_3 & = b_3
\end{matrix}
$$
**la primera ecuación para $x_1$**
$$
x_1 = \frac{b_1-a_{12}x_2-a_{13}x_3}{a_{11}}
$$
**la segunda ecuación para $x_2$**
$$
x_2=\frac{b_2-a_{21}x_1-a_{13}x_3}{a_{22}}
$$
**la tercera ecuación para $x_3$**
$$
x_3=\frac{b_3-a_{31}x_1-a_{33}x_2}{a_{33}}
$$
Se eligen valores iniciales para las $x$. Lo mas simple es suponer que todas las $x$ son cero.

Se calculan las nuevas $x​$ y se sustituyen en la siguiente iteración.

**Criterio de paro**
$$
|E_{a,k}|=\left|\frac{{x_k}^i-{x_k}^{i-1}}{{x_k}^i}\right|*100<E_s
$$

$$

$$
