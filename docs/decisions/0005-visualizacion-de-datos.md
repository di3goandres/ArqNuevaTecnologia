# Visualizacion de datos

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-20

## Context and Problem Statement

Se requiere de un modo de visualización para los siguientes contextos:
1. Análisis de datos para toma de decisiones
2. Monitoreo de sistemas en tiempo real.

## Decision Drivers

* RF-001 Componente de visualización en tiempo real

## Considered Options

* MVC

## Decision Outcome

Chosen option: "MVC"

### Positive Consequences

* Separación de responsabilidades
* Reutilización de componentes: La división del código en modelos, vistas y controladores facilita la reutilización de componentes en diferentes partes de la aplicación. Por ejemplo, se puede utilizar el mismo modelo de datos en diferentes vistas o emplear diferentes controladores para manejar distintos escenarios de interacción. Esto aumenta la eficiencia y agilidad en el desarrollo
* Facilidad de mantenimiento: El patrón MVC ayuda a reducir la complejidad del código y mejora la mantenibilidad de la aplicación. Al tener una separación clara de las responsabilidades, resulta más sencillo realizar cambios o mejoras en una parte del sistema sin afectar a las demás. Además, al contar con componentes bien definidos, la depuración y el seguimiento de errores se simplifican.
* Flexibilidad y escalabilidad: La arquitectura MVC permite que cada componente pueda ser desarrollado, probado y modificado de forma independiente. Esto facilita la evolución y adaptación de la aplicación a medida que los requisitos cambian o se agregan nuevas funcionalidades. Además, la separación de responsabilidades facilita la escalabilidad, ya que es posible agregar nuevos modelos, vistas o controladores sin afectar los demás componentes.
