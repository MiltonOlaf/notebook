# Reglas de producción
Es un método procedimental de representación del conocimiento que pone énfasis en representar y soportar las relaciones diferenciales en contraposición a los métodos declarativos o hechos, las reglas de producción son de si entonces, si se cumplen las condiciones se ejecutan las acciones.
La inferencia en los sistemas basados en reglas se realizan mediante el emparejamiento.
- Sistema de entrenamiento hacia adelante. Una regla es activada si los antecedentes emparejan con algunos hechos.
- Sistemas de emparejamiento hacia atrás. Una regla es activada si los consecuentes emparejan con algunos hechos

## Características de las reglas de producción
- Modularidad. Pequeñas cantidades de conocimiento relativamente independencia.
- Incremetabilidad. En esta es posible añadir o cambiar reglas con relativa independencia.
- Naturalidad y transparencia. Esta se refiere a la representación del conocimiento próxima y comprensible por las personas.
- Capacidad de generar explicaciones.

---

## Arquitectura de los sistemas basados en reglas
- Base de conocimiento. Reúne todo el conocimiento del sistema.
- Memoria activa. Contiene los hechos que representan el estado actual del problema y las reglas.
- Motor de inferencia. Decide que reglas se ejecutaran.

### Reglas
Una regla es definida como una representación estratégica o técnica la cual es apropiada cuando el conocimiento con el que deseamos trabajar proviene de la experiencia o intuición por lo tanto carece de una demostración física o matemática.

#### Tipos de proposiciones
Las proposiciones se pueden clasificar en los siguientes grupos.
- Proposiciones cualificadas son las que introducen un atributo para cualificar la proposición que forma una red. El atributo corresponde al grado que determina la regla es decir, grado de suceso, que puede ser probable o poco probable.
- Proposiciones cuantificadas. Estas indican cantidades difusas en las reglas.

### Tipos de Reglas
- **Con excepciones**. Del tipo si la temperatura es alta, hace calor, a menos que se tenga aire acondicionado.
- **Graduales**. Entre mas partidos se ganen mas fácil es ganar una liga.
- **Conflictiva**. Estas son reglas que mediante un mismo tipo de información contienen información contradictoria lo cual puede acarrear mucho problemas como arrastrar resultados. Este tipo de regla son aquellas que para un mismo antecedente tienen consecuentes distintos.

a