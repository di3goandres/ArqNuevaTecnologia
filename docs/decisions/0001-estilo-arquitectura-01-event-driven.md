# Estilo De Arquitectura

* Status: proposed
* Deciders: Julian luna, Diego Montealegre
* Date: 2023-06-16

## Context and Problem Statement

Necesitamos recolectar los eventos que se generan en los diferentes dispositivos de IoT

## Decision Drivers

* RF-005 Orquestación/ manejo de eventos de los sensores
* RF-006 Recepción de eventos de sensores IoT

## Considered Options

* Event driven

## Pros and Cons of the Options

### Event driven

* Good, because Desacoplamiento: La arquitectura de eventos permite un mayor desacoplamiento entre los diferentes componentes del sistema. Cada componente puede enviar y recibir eventos de forma independiente, lo que reduce la dependencia directa entre ellos. Esto facilita la evolución y actualización de los componentes de manera individual, sin afectar al funcionamiento de todo el sistema.
* Good, because Escalabilidad: Al utilizar una arquitectura de eventos, los componentes pueden escalar de manera independiente según la carga de trabajo. Los eventos se pueden distribuir y procesar de forma paralela, lo que permite manejar grandes volúmenes de eventos de manera eficiente. Además, se pueden agregar o quitar componentes de manera fácil y flexible según las necesidades de escalabilidad del sistema.
* Good, because Reactividad: Al basarse en eventos, el sistema puede responder de manera rápida y proactiva a los cambios y sucesos en la factoría. Los componentes pueden estar a la espera de eventos relevantes y tomar acciones inmediatas en función de ellos. Esto permite una mejor capacidad de respuesta y adaptabilidad a eventos en tiempo real, como alarmas de sensores, cambios en el estado de la producción, etc
* Good, because Integración y extensibilidad: La arquitectura de eventos facilita la integración de nuevos componentes y servicios en el sistema. Los eventos actúan como puntos de integración, permitiendo la comunicación entre diferentes partes del sistema de manera sencilla. Además, es más fácil extender y agregar nuevas funcionalidades al sistema mediante la incorporación de nuevos componentes que generen y consuman eventos.
* Good, because Tolerancia a fallos: La arquitectura de eventos puede proporcionar mayor tolerancia a fallos. Si un componente no puede procesar un evento en un momento dado, este se puede encolar y procesar más tarde, evitando la pérdida de información crítica. Además, si un componente falla, los eventos pendientes pueden ser procesados por otros componentes disponibles, evitando interrupciones en el funcionamiento del sistema

