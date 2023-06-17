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
* Rest

## Decision Outcome

Chosen option: "Event driven", because Reactividad en tiempo real: Una arquitectura event-driven está diseñada para manejar eventos en tiempo real y responder de manera reactiva a ellos. En un entorno de factoría inteligente, donde se requiere una notificación inmediata de eventos críticos, como alarmas de sensores, cambios en el estado de la producción o fallos en los equipos, una arquitectura event-driven puede proporcionar una mejor capacidad de respuesta y adaptabilidad.

Escalabilidad y rendimiento: La arquitectura event-driven permite una mayor escalabilidad y rendimiento al distribuir y procesar eventos de manera eficiente. Los eventos pueden ser manejados de forma paralela y distribuida entre los diferentes componentes del sistema, lo que facilita la gestión de grandes volúmenes de eventos en tiempo real. Esto es especialmente importante en una factoría inteligente con múltiples líneas de producción y sensores generando datos constantemente.

Desacoplamiento y evolución: La arquitectura event-driven fomenta el desacoplamiento entre los componentes del sistema. Cada componente puede emitir y consumir eventos de forma independiente, lo que facilita la evolución y actualización de los componentes de manera individual sin afectar al resto del sistema. Esto permite una mayor flexibilidad y adaptabilidad a medida que los requisitos del sistema evolucionan con el tiempo

Integración y extensibilidad: La arquitectura event-driven proporciona un mecanismo de integración flexible y extensible. Los eventos actúan como puntos de integración, permitiendo la comunicación entre diferentes partes del sistema de manera sencilla. Además, la adición de nuevos componentes que generen y consuman eventos se vuelve más fácil y menos disruptiva, lo que facilita la ampliación y mejora del sistema en el futuro.

Notificaciones en tiempo real y mensajería: En un sistema de factoría inteligente, es fundamental contar con notificaciones en tiempo real y un sistema de mensajería para mantener a los operarios informados sobre el estado de la producción, fallos en los sensores y otros eventos relevantes. Una arquitectura event-driven puede proporcionar una base sólida para implementar un sistema de notificaciones y mensajería en tiempo real, permitiendo una comunicación eficiente y oportuna.

## Pros and Cons of the Options

### Event driven

* Good, because Desacoplamiento: La arquitectura de eventos permite un mayor desacoplamiento entre los diferentes componentes del sistema. Cada componente puede enviar y recibir eventos de forma independiente, lo que reduce la dependencia directa entre ellos. Esto facilita la evolución y actualización de los componentes de manera individual, sin afectar al funcionamiento de todo el sistema.
* Good, because Escalabilidad: Al utilizar una arquitectura de eventos, los componentes pueden escalar de manera independiente según la carga de trabajo. Los eventos se pueden distribuir y procesar de forma paralela, lo que permite manejar grandes volúmenes de eventos de manera eficiente. Además, se pueden agregar o quitar componentes de manera fácil y flexible según las necesidades de escalabilidad del sistema.
* Good, because Reactividad: Al basarse en eventos, el sistema puede responder de manera rápida y proactiva a los cambios y sucesos en la factoría. Los componentes pueden estar a la espera de eventos relevantes y tomar acciones inmediatas en función de ellos. Esto permite una mejor capacidad de respuesta y adaptabilidad a eventos en tiempo real, como alarmas de sensores, cambios en el estado de la producción, etc
* Good, because Integración y extensibilidad: La arquitectura de eventos facilita la integración de nuevos componentes y servicios en el sistema. Los eventos actúan como puntos de integración, permitiendo la comunicación entre diferentes partes del sistema de manera sencilla. Además, es más fácil extender y agregar nuevas funcionalidades al sistema mediante la incorporación de nuevos componentes que generen y consuman eventos.
* Good, because Tolerancia a fallos: La arquitectura de eventos puede proporcionar mayor tolerancia a fallos. Si un componente no puede procesar un evento en un momento dado, este se puede encolar y procesar más tarde, evitando la pérdida de información crítica. Además, si un componente falla, los eventos pendientes pueden ser procesados por otros componentes disponibles, evitando interrupciones en el funcionamiento del sistema

### Rest

* Good, because Interoperabilidad: REST utiliza protocolos y estándares web ampliamente adoptados, como HTTP y JSON, lo que facilita la interoperabilidad con diferentes sistemas y tecnologías. Esto significa que el sistema de la factoría inteligente puede comunicarse y compartir datos de manera efectiva con otros sistemas externos, como sistemas de gestión de inventario, servicios en la nube u otros sistemas de la empresa.
* Good, because Simplificación de la comunicación: REST proporciona una interfaz uniforme y basada en recursos que simplifica la comunicación entre los diferentes componentes del sistema. Los componentes pueden interactuar a través de operaciones HTTP estándar, como GET, POST, PUT y DELETE, utilizando URLs bien definidas para acceder y manipular recursos. Esto facilita la comprensión y el desarrollo de la lógica de comunicación entre los componentes del sistema
* Bad, because Comunicación síncrona: REST se basa en una comunicación síncrona mediante el intercambio de solicitudes y respuestas entre el cliente y el servidor. En un entorno de factoría inteligente con múltiples sensores y componentes que generan eventos en tiempo real, la comunicación síncrona puede no ser eficiente ni escalable. La necesidad de una respuesta inmediata para cada solicitud puede generar cuellos de botella y afectar la capacidad de respuesta del sistema.
* Bad, because Notificaciones en tiempo real: REST no es inherentemente adecuado para proporcionar notificaciones en tiempo real. Si se requiere que los operarios de la factoría sean notificados instantáneamente sobre eventos críticos, como fallos en los sensores o sobrecarga en la producción, puede ser necesario establecer conexiones persistentes o utilizar mecanismos de polling frecuente, lo que puede ser ineficiente y aumentar la carga en el sistema.
* Bad, because Acoplamiento entre componentes: En una arquitectura REST, los componentes suelen estar acoplados a las URLs y estructuras de recursos específicas. Esto puede llevar a una mayor dependencia entre los componentes y dificultar la evolución y actualización individual de cada uno. En un entorno de factoría inteligente, donde la adaptabilidad y la flexibilidad son fundamentales, puede ser beneficioso tener una arquitectura más desacoplada y modular.
* Bad, because Complejidad en la gestión de estados: REST es una arquitectura sin estado, lo que significa que cada solicitud se considera independiente y no almacena información de estado en el servidor. En un sistema en el que se requiere mantener y gestionar el estado de la producción, las órdenes de trabajo y el inventario, el enfoque sin estado de REST puede requerir soluciones adicionales para mantener y sincronizar los estados, lo que puede aumentar la complejidad del sistema.
* Bad, because Escalabilidad en eventos y streaming de datos: Si el sistema de la factoría inteligente genera y procesa grandes volúmenes de eventos o datos en streaming, REST puede no ser la mejor opción. La comunicación basada en solicitudes y respuestas individuales puede ser ineficiente y no escalable en este contexto. Se pueden requerir enfoques más especializados, como arquitecturas basadas en eventos o streaming, para manejar eficientemente este tipo de casos de uso
