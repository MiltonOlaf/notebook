---
date: 2019-03-01
title: Composición de transformaciones bidimensionales
---
# Composición de transformaciones bidimensionales

## Traslaciones, rotaciones y escalaciones

### Composicion de traslaciones bidimensionales
Si dos vectores de traslación sucesivos son aplicados a dos $(t_{1x}, t_{1y})$ y $(t_{2x}, t_{2y})$ se aplica a una posición de coordenadas $P$, $P'$ es las transformación final y es calculada como:

$$
P' = T(t_{2x}, t_{2y}) * T(t_{1x}, t_{1y}) * P
$$
Donde $P$ y $P'$ son representadas como vectores como coordenadas homogéneas 3 elementos. Se puede verificar este resultado calculando la matriz producto para los dos grupos asociativos. Ademas la matriz de transformación compuesta para esta secuencia de traslación es:
$$
\begin{bmatrix}
1 & 0 & t_{2x} \\
0 & 1 & t_{2y} \\
0 & 0 & 1
\end{bmatrix}
*
\begin{bmatrix}
1 & 0 & t_{1x} \\
0 & 1 & t_{1y} \\
0 & 0 & 1
\end{bmatrix}
=
\begin{bmatrix}
1 & 0 & t_{1x}+t_{2x} \\
0 & 1 & t_{1y}+t_{2x} \\
0 & 0 & 1
\end{bmatrix} \\
$$

## Composición de rotación bidimencional

Dos rotaciones sucesivas aplicadas a un punto $P$ producen la posición transformada igual a la rotación:
$$
P' = R(\theta_2) * R(\theta_1) * P
$$
Al multiplicar las dos matrices de rotación se puede verificar que las dos sucesiones son sucesivas, dado que son aditivas para que las coordenadas rotadas finales de un punto puedan ser calculadas por la matriz de rotación compuesta como:
$$
P' = R(\theta_1 + \theta_2) * P
$$

## Composición de escalación bidimencional 

La concatenación de matrices para las transformaciones de dos operaciones de escalamiento sucesivas en dos dimensiones produce la siguiente matriz de escalación compuesta.
$$
\begin{bmatrix}
s_{x_2} & 0 & 0 \\
0 & s_{y_2} & 0 \\
0 & 0 & 1
\end{bmatrix}
*
\begin{bmatrix}
s_{x_1} & 0 & 0 \\
0 & s_{y_1} & 0 \\
0 & 0 & 1
\end{bmatrix}
=
\begin{bmatrix}
s_{1x}*s_{2x} & 0 & 0 \\
0 & t_{1y}*s_{2x} & 0 \\
0 & 0 & 1
\end{bmatrix} \\
$$

$$
S(S_{x_2}S_{y_2}) * S(S_{x_1}S_{y_1}) = S(S_{x_1} * S_{x_2}, S_{y_2} *S_{y_2})
$$



La matriz resultante en este caso que las sucesiones de escalas sucesivas son multiplicativas.

## Rotación de punto de pivote general

Para aplicar la rotación a un objeto que se encuentra afuera del origen, es necesario primero que el objeto sea trasladado al origen, después se aplica rotación y se regresa el objeto al punto pivote.
$$
\begin{bmatrix}
1 & 0 & x_1 \\
0 & 1 & y_1 \\
0 & 0 & 1
\end{bmatrix}
*
\begin{bmatrix}
\cos\theta & -\sin\theta & 0 \\
\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{bmatrix}
*
\begin{bmatrix}
1 & 0 & -x_1 \\
0 & 1 & -y_1 \\
0 & 0 & 1
\end{bmatrix} \\
=
\begin{bmatrix}
\cos\theta & -\sin\theta & -x_1\cos\theta + y_1\sin\theta + x_1 \\
\sin\theta & \cos\theta & -x_1\sin\theta - y_1\cos\theta + y_1 \\
0 & 0 & 1
\end{bmatrix} \\
$$
