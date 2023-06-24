# Seleccion Algoritmos - Strategy

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-20

## Context and Problem Statement

Se debe crear un UML que contenga el patron strategy para crear diferentes tipos de algoritmos de prediccion, y de entrenamiento

## Decision Drivers

* RF-002 Seleccion Algoritmos

## Decision Outcome

Chosen option: "Strategy"

### Positive Consequences

* Flexibilidad: Permite cambiar o seleccionar diferentes estrategias en tiempo de ejecución sin modificar el código existente del contexto.
* Reutilización de código: Los algoritmos se encapsulan en estrategias reutilizables que pueden ser utilizadas por diferentes contextos o componentes.
* Extensibilidad: Permite agregar nuevas estrategias sin modificar el código existente, simplemente implementando una nueva estrategia y configurándola en el contexto.
* Facilidad de mantenimiento: Al separar la implementación de los algoritmos de la clase principal, se facilita la comprensión, el mantenimiento y la evolución del sistema.

### Negative Consequences

* Toma de decisiones: El desarrollador debe tener en cuenta cuándo y cómo seleccionar la estrategia adecuada para un contexto particular, ya que esta responsabilidad recae en el código que configura el contexto.
