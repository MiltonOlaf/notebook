---
title: Solución de ecuaciones diferenciales
---

Solucionar ecuaciones con diferenciales ordinarias de la forma
$$
\frac{dy}{dx} = f(x,y)
$$
La forma general para dar solución a estas ecuaciones es: 
$$
\text{Nuevo valor} = \text{Valor anterior} + \text{Pendiente} * \text{Tamaño de paso}
$$
$$
Y_{i+1} = Y_i + \phi h
$$
La pendiente estimada $\phi$ se usa para extrapolar desde un valor anterior $Y_i$ a un nuevo valor $Y_{i+1}$ en una distancia $h$. Esta formula se aplica paso a paso para calcular un valor posterior y, por lo tanto, parra trazar la trayectoria de la solución.
