---
title: Polinomios de interpolación de Newton
---

El polinomio de n-ésimo grado es
$$
  fn(x) = b_0 + b_1(x-x_0)+ \ldots +
$$

## Ejemplo
Determine polinomios de interpolación de Newton de segundo, tercer y cuarto orden para obtener y en $x = 3.5$.

| $x$  | 0    | 1      | 2.5    | 3     | 4.5    | 5      | 6    |
| :--- | :--- | :----- | :----- | :---- | :----- | :----- | :--- |
| $y$  | 2    | 5.4375 | 7.3516 | 75625 | 8.4453 | 9.1875 | 12   |

***No es necesario que los datos estén igualmente espaciados ni que estén ordenados en forma ascendente.***

| $i$  | $x_i$ | $f(x_1)$ | Primero                              | Segundo                                | Tercero                               | Cuarto                         |
| :--- | :---- | :------- | :----------------------------------- | :------------------------------------- | :------------------------------------ | :----------------------------- |
| 0    | 1     | 5.4375   | $\frac{7.3516-7.4345}{2.5-1}=1.2761$ | $\frac{0.4218-1.2761}{3-1}=-0.4272$    | $\frac{0.0834-0.4272}{4.5-1}=-0.0982$ | $\frac{0.1458-(-0.0982)}{5-1}$ |
| 1    | 2.5   | 7.3516   | $\frac{7.5625-7.3516}{3-2.5}=0.4218$ | $\frac{0.5885-0.4218}{4.5-2.5}=0.0834$ |

# Ejercicio

| Tiempo                | 10   | 15   | 20   | 25   | 40   | 50   | 55   | 60   | 75   |
| :-------------------- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Esfuerzo a la tension | 5    | 20   | 18   | 40   | 33   | 54   | 70   | 60   | 78   |