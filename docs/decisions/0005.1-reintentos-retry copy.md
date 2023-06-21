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

* MVC - Angular
* MVC - React

## Decision Outcome

Chosen option: "MVC - React"

### Positive Consequences

* Reutilización de componentes: React se basa en la idea de componentes reutilizables, lo que permite crear piezas de interfaz de usuario independientes y modularizadas. Estos componentes pueden ser utilizados en diferentes partes de la aplicación, lo que facilita la reutilización de código y acelera el desarrollo.
* Eficiencia de rendimiento: React utiliza un Virtual DOM (Documento de Objeto Modelo) para realizar actualizaciones eficientes en la interfaz de usuario. En lugar de actualizar todo el DOM, React identifica y actualiza solo los componentes que han cambiado. Esto mejora el rendimiento de la aplicación, especialmente cuando se trabaja con grandes conjuntos de datos.
* Comunidad y ecosistema activos: React cuenta con una gran comunidad de desarrolladores y un ecosistema activo de bibliotecas y herramientas. Esto significa que hay una amplia gama de recursos, documentación y ejemplos disponibles, lo que facilita el aprendizaje y la resolución de problemas
* Flexibilidad y escalabilidad: React es una biblioteca y no un framework completo, lo que brinda a los desarrolladores flexibilidad para elegir las herramientas y bibliotecas adicionales que deseen utilizar. Esto permite adaptar la aplicación a las necesidades específicas del proyecto y escalarla de manera efectiva a medida que crece

### Negative Consequences

* Curva de aprendizaje inicial: Si bien React tiene una curva de aprendizaje relativamente baja en comparación con otros frameworks, como Angular, aún requiere cierto tiempo y esfuerzo para comprender sus conceptos fundamentales, como los componentes, el estado y las propiedades.
* Configuración inicial: A diferencia de los frameworks más completos, React no proporciona una estructura predefinida ni una solución completa para todas las necesidades de una aplicación. Esto significa que es necesario configurar y elegir herramientas adicionales, como enrutadores o bibliotecas de administración de estado, lo que puede requerir tiempo y conocimiento adicional.
* Mayor responsabilidad del desarrollador: React se centra en la capa de vista y no incluye soluciones predefinidas para aspectos como el enrutamiento, la administración del estado o la comunicación con el servidor. Esto significa que los desarrolladores tienen una mayor responsabilidad en la elección y configuración de estas herramientas adicionales.
* Mayor complejidad en aplicaciones grandes: A medida que una aplicación React crece en tamaño y complejidad, puede volverse más difícil de mantener y organizar el código. Sin una estructura clara y predefinida, es importante seguir buenas prácticas y patrones de diseño para mantener un código limpio y mantenible.

## Pros and Cons of the Options

### MVC

* Good, because Framework completo: Angular es un framework completo que proporciona una estructura y un conjunto de herramientas bien definidos para el desarrollo de aplicaciones. Proporciona características listas para usar para la visualización de datos, como directivas, enlace de datos bidireccional y manejo de eventos.
* Good, because Tipo seguro y productividad: Angular utiliza TypeScript, que agrega tipado estático al desarrollo de JavaScript. Esto ayuda a identificar errores en tiempo de compilación y mejorar la productividad del desarrollo, especialmente en proyectos más grandes. Además, Angular proporciona herramientas para la generación automática de código y scaffolding, lo que acelera el proceso de desarrollo.
* Good, because Inyección de dependencias y modularidad: Angular facilita la inyección de dependencias y la creación de módulos, lo que favorece la reutilización y la organización del código en la visualización de datos. Esto permite crear componentes altamente modulares y facilita la colaboración entre equipos de desarrollo.
* Good, because Componentes reutilizables: React se basa en la idea de componentes reutilizables, lo que permite crear visualizaciones de datos modulares y flexibles. Los componentes de React se pueden componer fácilmente para construir interfaces de usuario interactivas y dinámicas.
* Good, because Virtual DOM eficiente: React utiliza un Virtual DOM (Documento de Objeto Modelo) para realizar actualizaciones eficientes en la interfaz de usuario. Esto resulta beneficioso cuando se trabaja con grandes conjuntos de datos, ya que React optimiza el rendimiento al actualizar solo los componentes que han cambiado, minimizando la carga en el navegador.
* Good, because Amplia comunidad y ecosistema: React cuenta con una gran comunidad de desarrolladores y una amplia gama de bibliotecas y herramientas disponibles. Esto facilita la integración de bibliotecas de visualización de datos populares, como D3.js o Chart.js, y la colaboración con otros desarrolladores.
* Bad, because Mayor curva de aprendizaje inicial: Angular tiene una curva de aprendizaje más pronunciada en comparación con React, ya que es un framework más completo y requiere un mayor entendimiento de los conceptos y las prácticas recomendadas de Angular.
* Bad, because Mayor complejidad y código más extenso: Angular tiene una estructura más compleja en comparación con React, lo que puede resultar en más código y archivos para administrar. Esto puede llevar a una mayor complejidad y dificultad en proyectos más pequeños o sencillos.
* Bad, because Curva de aprendizaje inicial: Para los desarrolladores nuevos en React, puede haber una curva de aprendizaje inicial para comprender los conceptos y las mejores prácticas de desarrollo. La adopción de herramientas y bibliotecas adicionales para la visualización de datos también puede requerir tiempo de aprendizaje adicional.
* Bad, because Mayor responsabilidad del desarrollador: React es una biblioteca y no un framework completo, lo que significa que el desarrollador tiene mayor responsabilidad en la elección de herramientas, administración del estado y estructura de la aplicación. Esto puede requerir una planificación cuidadosa y una toma de decisiones adecuada para la visualización de datos
