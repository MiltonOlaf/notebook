# Para que se usan ciertos números
Se usan como una fuente confiable de maleabilidad dentro de los modelos de simulación fundamentalmente porque las sucesiones de números pseudo-aleatorios son mas rápidas de generar que la de los números aleatorios.
La simulación es el proceso de diseñar un modelo de un sistema real que servirá para dirigir experimentos con el propósito de entender, explicar, analizar o mejorar el comportamiento del sistema.
Para simular el comportamiento de una o mas variables aleatorias es necesario contar con un conjunto suficientemente grande de números aleatorios, pero por desgracia generar una sucesión de números que sean completamente aleatorios resulta muy complicado ya que tendríamos que generar una sucesión infinita de valores que nos permitiera comprobar la inexistencia de correlaciones entre ellos, lo que seria costoso y tardado, volviendo impracticable la simulación; por ello es necesario utilizar los números pseudo-aleatorios de los cuales podemos asegurar con un nivel alto de confiabilidad que se comportan de manera similar a un conjunto de números aleatorios. La experimentación directa sobre la realidad genera algunos tipos de problemas como: Costo muy alto, gran lentitud, en ocasiones las pruebas son destructivas, puede no ser ética (sobre todo si están involucrados seres humanos), puede resultar imposible, como por ejemplo, para predecir sucesos futuros.

# Como se generan los números pseudo-aleatorios entre 0 y 1?
Los números pseudo-aleatorios se generan mediante algoritmos deterministicos, es aquellos en los que se obtiene el mismo resultado bajo las mismas condiciones iniciales por lo cual requieren parámetros de arranque.
Sea una secuencia $r = {r1, r2, r3 ... rn}$ se le conoce como el conjunto necesario de números entre 0 y 1 para realizar una simulación, siendo $n$ el periodo o ciclo de vida.
Esta secuencia forma la parte principal de la simulación de procesos estocásticos (basado en probabilidades) y son usados para generar la conducta de variables aleatorias continuas o discretas. Estos números se consideran pseudo-aleatorios porque es imposible el generar números realmente aleatorios es preciso contar con un conjunto $r_i$ grande, esto con la finalidad de simular el comportamiento d una o mas variables aleatorias. Ademas el periodo de vida debe ser alto debido a que es conveniente realizar varias replicas de simulación, corriendo cada una con números pseudo-aleatorios distintos es importante señalar que ni se considera satisfactorio si pasa sin problema las pruebas de uniformidad y dependencia, solo así podrá ser usado en la simulación.
Los algoritmos deterministicos para generar números pseudo-aleatorios se dividen en nocongruenciales y congruenciales, estos a su vez se dividen en lineales y no lineales.

# Algoritmos no congruenciales

## Algoritmo de cuadrados medios.
Propuesto en la época de los 40 del siglo XX por Von Neumann y Metrópolis, este algoritmo requiere un numero entero, llamado semilla, con $D$ dígitos este es elevado al cuadrado para seleccionar del resultado los $D$ dígitos del centro; El primer numero $n_i$ se determina simplemente anteponiendo el "0" a estos dígitos para obtener el segundo $n_i$ se sigue el mismo procedimiento, solo que ahora se elevan al cuadrado los $D$ dígitos del centro que se seleccionaro para obtener el primer $n_i$. Este método se repite hasta obtener $n$ numero $r_i$.

### Pasos para generar números
- Seleccionar semilla ($X_0$) a continuación con $D$ ($D > 3$).
- Sea $X0 = {X_0}^2$; sea $X_0 = D$ dígitos y sea $r_i = 0. D$ dígitos del centro.
- Sea $Y_i = {Y_i}^2$; Sea $X_i + 1 = los D$ dígitos del centro y sea $r_i = 0. D$ dígitos del centro.
- Repetir el paso 3 hasta obtener $n$ números $r_i$ deseados ejemplo

Nota: Si no es posible obtener los $D$ dígitos del centro del numero $Y_i$ agregue 0 a la izquierda del numero $Y_i$.

Ejemplo. Generar los primero  5 números $n_0$ a partir de $X_0$ de donde se puede observar que $D = 4$ dígitos.

$Y$ | $X$ | $r$
-- | -- | --
$Y_0 = (5735)^2 = 32890225$ | $X_1 = 8902$ | $r_1 = 0.8902$ |
$Y_1 = (8902)^2 = 79245604$ | $X_2 = 2456$ | $r_2 = 0.2456$ |
$Y_2 = (2456)^2 = 6031936$ | $X_3 = 0319$ | $r_3 = 0.0319$ |
$Y_3 = (0319)^2 = 00101761$ | $X_4 = 1017$ | $r_4 = 0.1017$ |
$Y_4 = (1017)^2 = 01034289$ | $X_5 = 0342$ | $r_5 = 0.0342$ |

Generalmente este algoritmo es incapaz de generar una secuencia de $r_i$ con periodo de vida $n$ grande en ocasiones solo es capaz de generar un numero por ejemplo si $X_0 = 1000$, entonces $X_1 = 0000$; $r_i = 0.0000$ y se dice que el algoritmo se degenera con la semilla de $X_0 = 1000$


#### Tarea
$Y​$ | $X​$ | $r​$
-- | -- | --
$Y_0 = (317)^2 = 100489​$ | $X_1 = 0048​$ | $r_1 = 0.0048​$ |
$Y_1 = (048)^2 = 02304​$ | $X_2 = 0230​$ | $r_2 = 0.0230​$ |
$Y_2 = (230)^2 = 52900​$ | $X_3 = 5290​$ | $r_3 = 0.5290​$ |
$Y_3 = (290)^2 = 0168100​$ | $X_4 = 9841​$ | $r_4 = 0.9841​$ |

$Y_4 = (410)^2 = 96845281$ | $X_5 = 8452$ | $r_5 = 0.8452$ |
---
## Algoritmo de productos medios
La mecánica de generación de números pseudo-aleatorios de este algoritmo no congruencial es similar a la del algoritmo de cuadrados medios la diferencia entre ambos radica en que el algoritmo de productos medios requiere de dos semillas ambas con $D$ dígitos; ademas, en lugar de elevarlos al cuadrado, las semillas se multiplican y del producto se seleccionan los $D$ dígitos del centro.

A continuación se presentan con mas detalle los del método para generar números con este algoritmo.

- Seleccionar una semilla ($X_0$) con ($D>3$).
- Seleccionar una semilla ($X_1$) con ($D>3$).
- $Y_0 = X_0 * X_1$; Sea $X_2$ = los $D$ dígitos del centro, y se $r_i = 0.D$ dígitos del centro.
- $Y_0 = X_0 + X_1$; Sea $X_2$ = los $D$ dígitos del cetro, y sea $r_i$  = 0.$D$ dígitos del centro.  
- Sea $Y_i$ = $X_i * X_{i+1}$ y sea $X_{i+2} =$ los $D$ dígitos del centro. y sea $r_{i+2} = 0.D$ dígitos del centro.
- Repetir el paso 4 hasta obtener los $n$ números $r_i$ deseados.  
*Nota: Si no es posible obtener los $D$ dígitos del centro, agregue 0s a la izquierda del número $r_i$.*

Generar los primeros 5 números $r_i$ a partir de las semillas $X_0 = 5015$ y $X_1 = 5734$, siendo $D = 4$.

$Y_n$ | $X_n$ | $r_n$ |
:- | :- | :- |
$Y_0 = 5015*5734 = 28756010$ | $X_2 = 7560$ | $r_1 = 0.7560$
$Y_1 = 5734*7560 = 43349049$ | $X_3 = 3490$ | $r_2 = 0.3490$
$Y_2 = 7560*3490 = 26384400$ | $X_4 = 3844$ | $r_3 = 0.3844$
$Y_3 = 3490*3844 = 13425560$ | $X_5 = 4255$ | $r_4 = 0.4255$
$Y_4 = 3844*4255 = 16356200$ | $X_6 = 3562$ | $r_5 = 0.3562$

Ejercicio. Generar los primeros 5 números $R_i$ a partir de las semillas $X_0 = 36$ y $X_1 = 97$, con $D = 2$.

$Y_n$ | $X_n$ | $r_n$
:- | :- | :-
$Y_0 = 36*97 = 3492$ | $X_2 = 49$ | $r_1 = 0.49$
$Y_1 = 97*49 = 4753$ | $X_3 = 75$ | $r_2 = 0.75$
$Y_2 = 49*75 = 3675$ | $X_4 = 67$ | $r_3 = 0.67$
$Y_3 = 75*67 = 5025$ | $X_5 = 02$ | $r_4 = 0.02$
$Y_4 = 67*02 = 0134$ | $X_6 = 13$ | $r_5 = 0.13$


### Algoritmo de multiplicador constante
Este algoritmo no congruencial es similar al algoritmo de productos medios. Los siguientes son los pasos necesarios para generar números pseudoaleatorios con el algoritmo multiplicador constante.  
1. S

$Y_n$ | $X_n$ | $r_n$
:- | :- | :-
$Y_0 = 2010*5340 = 10733400$ | $X_1 = 7334$ | $r_1 = 0.7344$
$Y_1 = 2010*7334 = 14741340$ | $X_2 = 7413$ | $r_1 = 0.7413$
$Y_2 = 2010*7413 = 14900130$ | $X_3 = 9001$ | $r_2 = 0.9001$

$Y_n$ | $X_n$ | $r_n$
:- | :- | :-
$Y_0 = 6965*9803 = 68277895$ | $X_1 = 2778$ | $r_1 = 0.2778$
$Y_1 = 6965*2778 = 19348770$ | $X_2 = 3487$ | $r_2 = 0.3487$
$Y_2 = 6965*3487 = 24286955$ | $X_3 = 2869$ | $r_3 = 0.2869$
$Y_3 = 6965*2869 = 19982585$ | $X_4 = 9825$ | $r_4 = 0.9825$
$Y_4 = 6965*9825 = 68431125$ | $X_5 = 4311$ | $r_5 = 0.4311$

### Algoritmo lineal
Este algoritmo congruencias fue propuesto por D.H. Lehmer en 1951.
Segun Law y Kelton, este algoritmo ha sido el mas usado. El algoritmo congruencial lineal genera un secuencia de números enteros por medio de la siguiente ecuación.
\[
\ {X_i+1 = (aX_1+c) * mod(m)}
\ i = 1,2,3
\
\ X_0 = semilla X_0 > 0
\]
