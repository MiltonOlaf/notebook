# Para que se usan ciertos números
Se usan como una fuente confiable de maleabilidad dentro de los modelos de simulación fundamentalmente porque las sucesiones de números pseudo-aleatorios son mas rápidas de generar que la de los números aleatorios.
La simulación es el proceso de diseñar un modelo de un sistema real que servirá para dirigir experimentos con el propósito de entender, explicar, analizar o mejorar el comportamiento del sistema.
Para simular el comportamiento de una o mas variables aleatorias es necesario contar con un conjunto suficientemente grande de números aleatorios, pero por desgracia generar una sucesión de números que sean completamente aleatorios resulta muy complicado ya que tendríamos que generar una sucesión infinita de valores que nos permitiera comprobar la inexistencia de correlaciones entre ellos, lo que seria costoso y tardado, volviendo impractica la simulación; por ello es necesario utilizar los números pseudo-aleatorios de los cuales podemos asegurar con un nivel alto de confiabilidad que se comportan de manera similar a un conjunto de números aleatorios. La experimentación directa sobre la realidad genera algunos tipos de problemas como: Costo muy alto, gran lentitud, en ocasiones las pruebas son destructivas, puede no ser ética (sobre todo si están involucrados seres humanos), puede resultar imposible, como por ejemplo, para predecir sucesos futuros.

# Como se generan los números pseudo-aleatorios entre 0 y 1?
Los números pseudo-aleatorios se generan mediante algoritmos deterministicos, es aquellos en los que se obtiene el mismo resultado bajo las mismas condiciones iniciales por lo cual requieren parámetros de arranque.
Sea una secuencia $r = {r1, r2, r3 ... rn}$ se le conoce como el conjunto necesario de números entre 0 y 1 para realizar una simulación, siendo $n$ el periodo o ciclo de vida.
Esta secuencia forma la parte principal de la simulación de procesos estocásticos (basado en probabilidades) y son usados para generar la conducta de variables aleatorias continuas o discretas. Estos números se consideran pseudo-aleatorios porque es imposible el generar números realmente aleatorios es preciso contar con un conjunto $r_i$ grande, esto con la finalidad de simular el comportamiento d una o mas variables aleatorias. Ademas el periodo de vida debe ser alto debido a que es conveniente realizar varias replicas de simulación, corriendo cada una con números pseudo-aleatorios distintos es importante señalar que ni se considera satisfactorio si pasa sin problema las pruebas de uniformidad y dependencia, solo así podrá ser usado en la simulación.
Los algoritmos deterministicos para generar números pseudo-aleatorios se dividen en nocongruenciales y congruenciales, estos a su vez se dividen en lineales y no lineales.

# Algoritmos no congruenciales
- **Algoritmo de cuadrados medios**. Propuesto en la época de los 40 del siglo XX por Von Neumann y Metrópolis, este algoritmo requiere un numero entero, llamado semilla, con $D$ dígitos este es elevado al cuadrado para seleccionar del resultado los $D$ dígitos del centro; El primer numero $n_i$ se determina simplemente anteponiendo el "0" a estos dígitos para obtener el segundo $n_i$ se sigue el mismo procedimiento, solo que ahora se elevan al cuadrado los $D$ dígitos del centro que se seleccionaro para obtener el primer $n_i$. Este método se repite hasta obtener $n$ numero $r_i$.

## Pasos para generar números
- Seleccionar semilla ($X_0$) a continuación con $D$ ($D > 3$).
- Sea $X0 = {X_0}^2$; sea $X_0 = D$ dígitos y sea $r_i = 0. D$ dígitos del centro.
- Sea $Y_i = {Y_i}^2$; Sea $X_i + 1 = los D$ dígitos del centro y sea $r_i = 0. D$ dígitos del centro.
- Repetir el paso 3 hasta obtener $n$ números $r_i$ deseados ejemplo

Nota: Si no es posible obtener los $D$ dígitos del centro del numero $Y_i$ agregue 0 a la izquierda del numero $Y_i$.

Ejemplo. Generar los primero  5 números $n_0$ a partir de $X_0$ de donde se puede observar que $D = 4$ dígitos.

$Y$ | $X$ | $r$
-- | -- | --
$Y_0 = (5735)^2 = 32890225$ | $X_1 = 8902$ | $r_1 = 0.8902$ |
$Y_1 = (8902)^2 = 79245604$ | $X_2 = 8902$ | $r_2 = 0.8902$ |
$Y_2 = (5735)^2 = 32890225$ | $X_3 = 8902$ | $r_3 = 0.8902$ |
$Y_3 = (5735)^2 = 32890225$ | $X_4 = 8902$ | $r_4 = 0.8902$ |
$Y_4 = (5735)^2 = 32890225$ | $X_5 = 8902$ | $r_5 = 0.8902$ |

Generalmente este algoritmo es incapaz de generar una secuencia de $r_i$ con periodo de vida $n$ grande en ocasiones solo es capaz de generar un numero por ejemplo si $X_0 = 1000$, entonces $X_1 = 0000$; $r_i = 0.0000$ y se dice que el algoritmo se degenera con la semilla de $X_0 = 1000$
