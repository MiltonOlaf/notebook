<small>***08-02-2019***</small>

# Métodos abiertos

Se basan en formulas que requieren de un solo valor de inicio $x$ o que empiecen con un par de ellos, pero que no necesariamente encierran la raíz. Estos algunas veces divergen, a medida que se avanza en el cálculo. Sin embargo, cuando convergen en general lo hacen mucho mas rápido que los métodos cerrados.

## Iteración de punto fijo

Sea una ecuación $f(x) = 0$. 

Se arregla la ecuación de manera que $x = g(x)​$. 

**Ejemplo.**  $x^2 - 2x + 9 = 0$ 

$$
x = \frac{x^2 + 9}{2}
$$

$$
\sin{(x)^2} + 1 = 0
$$

$$
\sin{(x)^2} + 1 + x = x
$$

$$
g(x) => \sin{(x)^2} + 1 + x
$$

### Convergencia

La ecuación iterativa es:
$$
x_{i+1}= g(X_i)
$$

La solución verdadera es:
$$
x_r = g(X_r)
$$

Al restar las ecuaciones se tiene
$$
x_r-X_{i+1} = g(x_r)-g(x_i)
$$

Del teorema fundamental del cálculo
$$
g'(c) = \frac{g(b)-g(a)}{b-a}
$$

Si $a = X_i$ y $b=X_r$, entonces
$$
g'(c)= \frac{g(X_r) - g(X_i)}{X_r - X_i}
$$

$$
g(X_r) - g(X_i) = (X_r - X_i) * g'(c)
$$

Sustituyendo esto en la ecuación 1)
$$
x_r - X_{i+1} = (X_r - X_i) * g(c)
$$

$$
E_{t, i} = (X_r -X_i)
$$

$$
E_{t, i+1} = E_{t, i} * g'(c)
$$

Para que el método converja, se dbe cumplir $|g'(x)|<1$

### Ejercicio

Localice la raíz de:

$$f(x) = 2 \sin{(\sqrt{x})} - x$$

Haga una elección inicial de $X_0 = 0.5$ e itere hasta que $E_a < 0.01$%.
$$
2\sin{\sqrt{x}} = 0
$$

$$
x = 2\sin{\sqrt{x}} \quad \Rightarrow \quad x_{i+1}=\sin{\sqrt{x_i}}
$$

$$
x_{i+1} = g(x_i)
$$

| N°   | $x_i$     | $E_a$(%) | $x_i$           |
| :--- | :-------- | :------- | :-------------------------------------- |
| 0    | 0.5       | -        | $0.5$                               |
| 1    | 1.299274  | 61.52    | $2\sin{\sqrt{0.5}} = 1.299274$ |
| 2    | 1.817148  | 28.50    | $2\sin{\sqrt{1.299274}} = 1.187148$ |
| 3    | 1.9550574 | 6.48     | $2\sin{\sqrt{1.187148}} = 1.9550574$ |
|  4 | 1.969743 | 0.97 | $2\sin{\sqrt{1.955074}} = 1.969743$ |
|  5 | 1.972069 | 0.11|$2\sin{\sqrt{1.969743}} = 1.972069$ |
|  6 | 1.972344 | 0.013 | $2\sin{\sqrt{1.972069}} = 1.972344$ |
|  7 | 1.972377 | 0.0016| $2\sin{\sqrt{1.972344}} = 1.972377$ |

### Ejercicio
Determina la raíz real más grande de $f(x) = 2x^3 - 11.7x^2 + 17.7x -5$ con el método de punto fijo. 
$$
x = \frac{-2x^3 + 11.7x^2 + 5}{17.7}
$$
$$
x = g(x)
$$

<small>***11-02-2019***</small>

## Newton-Raphson

Se deduce a partir de la interpretación geométrica de la derivada.

![Método de Newton Raphson](/home/miltonolaf/github/outside/CSE-Notes/6th_Semester/Métodos Numericos/resources/newton_r_example.png)
$$
f'(x_i) = \frac{f(x_i)-0}{x_i - x_{i+1}}
$$

$$
x_{i+1} = X_i - \frac{f(x_i)}{f'(x_i)}
$$

*Nota: el error es proporcional al cuadrado del error anterior. Esto significa que el número de cifras decimales correctas aproximadamente se duplica en cada iteración. A este comportamiento se le llama convergencia cuadrática.*

### Ejercicio
Utilice el método de Newton-Raphson para determinar las raices de $2x \cos{2x} - (x-2)^2 = 0$, en $2 <= x <= 3$ y $3 <= x <= 4$ hasta que $E_a < 0.01​$%.

$$
f(x) = 2x\cos{2x} - (x-2)^2
$$

$$
f'(x) = -4x\sin{2x} + 2\cos{2x} -2(x-2)
$$

$$
x_{i+1} = X_i - \frac{2x \cos2x - (x-2)^2}{-4x \sin{2x} + 2\cos{2x}  2(x-2)}
$$

| N°   | $X_i$    | $E_a$ % |
| :--- | :------- | :------ |
| 00   | 2        | -       |
| 01   | 2.550769 | 21.59   |
| 02   | 2.371359 | 7.57    |
| 03   | 2.370587 | 0.0283  |
| 04   | 2.370686 | 0.00004 |

| N°   | $X_i$    | $E_a$ %   |
| :--- | :------- | :-------- |
| 00   | 4        | -         |
| 01   | 3.743349 | 6.85      |
| 02   | 3.722390 | 0.56      |
| 03   | 3.722113 | 0.0074420 |

## Secante

La derivada se puede aproximar mediante una diferencia finita hacia atrás.
$$
f'(x_i) =~ \frac{f(x_{i+1}) - f(x)}{x_{i+1}-x_i}
$$

Al sustituir la formula de Newton-Raphson:
$$
x_{i+1} = X_i - \frac{f(x_i)(X_{i-1} - X_i)}{f(x_{i-1}) - f(x_i)}
$$

| N°   | $X_{i-1}$ | $X_i$    | $f(X_{i-1})$ | $f(x_i)$  | $E_a$     |
| :--- | :-------- | :------- | :----------- | :-------- | :-------- |
| 00   | 2         | 3        | -2.614574    | 4.761022  | -         |
| 01   | 3         | 2.354490 | 4.761022     | -0.141717 | 27.416133 |
| 02   | 2.354490  | 2.373149 | -0.141717    | 0.021669  | 0.786249  |
| 03   | 2.373149  | 2.370674 | 0.021669     | -0.000113 | 0.104387  |
| 04   | 2.370674  | 2.370687 | -0.000113    | 0.0000007 | 0.000540  |