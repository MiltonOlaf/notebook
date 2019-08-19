---
date: 2019-05-17
title: Interpolacion
---

Estimar valores intermedios con valores asociados con datos.

### Interpolación polinomial

Polinomio de n-ésimo grado $f(x) = a_0 + a_1x+a_2x^2 + ... + a_nx^n$.

Dados $n+1$ puntos asociados con datos, hay uno u solo un polinomio de grado $n$ que pasa a través de todos los puntos.

### Interpolación lineal

Unir dos puntos asociados con datos con una linea recta.

$$
\frac{f(x)-f(x_0)}{x-x_0} = \frac{f(x_1)-f(x_0)}{x_1-x_0}
$$

$$
f_1(x) = f(x_0) + \frac{f(x_1)-f(x_0)}{x_1-x_0 \text{test}} (x-x_0)
$$

### Interpolación cuadrática

Si se tienen 3 puntos asociados con datos, estos pueden ajustarse en un polinomio de segundo grado.

Una forma conveniente es:

$$ f_2(x)=b_0+b_1(x-x_0)+b_2(x-x_0)(x-x_1) $$

$$ = b_0 + b_1x-b_1x_0+b_2(x2-x_1x-x_0x+x_0x_1) $$
$$ = b_0 + b_1x-b_1x_0+b_2x2-b_2x_1x-b_2x_0x+b_2+b_2x_0x_1 $$
$$ =(b_0-b_1x_0+b_2x_0x_1)+(b_1-b_2x_0-b_2x_1)x+b_2x2 $$

donde:

$$ a_0=b_0-b_1x_0+b_2x_0x_1 $$
$$ a_1=b_1-b_2x_0-b_2x_1 $$
$$ a_2=b_2 $$
$$ \text{Si} \quad x = x_0 $$
$$ \text{tenemos:} \quad b_0=f(x_0) $$
$$ \text{Si} \quad x=x_1$$
$$ f(x_1)=b_0+b_1(x_1-x_0) $$
$$ b_1=\frac{f(x1)-b_0}{x_1-x_0} $$
$$ b_1=\frac{f(x_1)-f(x_0)}{x_1-x_0} $$
$$ \text{Si} \quad x=x_1 $$
$$ f(x_1)=b_0+b_1(x_1-x_0) $$

$$ b_1=\frac{f(x_1)-b_0}{x_1-x_0} $$
$$ b_1=\frac{f(x_1)-f(x_0)}{x_1-x_0} $$

## Ejemplo

Ajuste polinomios de primer y segundo grado a los puntos:

| $x_0 = 1$ | $f(x_0)=0$          |
| --------- | ------------------- |
| $x_1=4$   | $f(x_1)=1.386294$   |
| $x_2=5$   | $f(x_2) = 1.609438$ |
| $x_3=6$   | $f(x_3)=1.791754$   |

Evalúe ambos en x = 2

$$ f_1(x) = 0 + \frac{1.386294 - 0}{4 - 1}(x-1) $$
$$ f_1(x) = 0.462098(x-1) $$
$$ f_1(x) = 0.46209 (2-1) = 0.462098 $$

Para el polinomio de segundo grado:

$$ b = 0 $$
$$ b_1 = \frac{1.386294 - 0}{4-1} = 0.462098$$
$$ b_2 = \frac{\frac{1.386294 - 1.386394}{25 - 4} - \frac{1.386294 - 0}{4 - 1}}{5-1} $$

$$ f_2(x) = 0 + 0.462098(x_1) + (-0.059739) (x-1)(x-4) $$
$$ f_2(x) = 0.462098(x_1) - 0.059730(x-1)(x-4) $$
$$ f_2(x) = 0.462098(2_1) - 0.059739(2-1)(2-4) = 0.581576 $$

## Tabla de interpolación de Newton

| $i$ | $x_1$ | $f(x_i)$ | Primer                                    | Segundo                                   | Tercero                                      |
| --- | ----- | -------- | ----------------------------------------- | ----------------------------------------- | -------------------------------------------- |
| 0   | 1     | 0        | $\frac{1.386284-0}{4-1}=0.462098$         | $\frac{0.223144-0.462098}{5-1}=-0.059739$ | $\frac{-0.020411-(-0.059739)}{6-1}=0.007865$ |
| 1   | 4     | 1.386294 | $\frac{1.609438-1.386294}{5-4} = 0.22344$ | $\frac{0.182321-0.223144}{6-4}=-0.020411$ |
| 2   | 5     | 1.609438 | $\frac{1.791759-1.609438}{6-5}=0.182321$  |                                           |
| 3   | 6     | 1.791759 |                                           |                                           |                                              |
