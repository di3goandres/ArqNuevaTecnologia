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


## Pros and Cons of the Options

### Rest

* Good, because Interoperabilidad: REST utiliza protocolos y estándares web ampliamente adoptados, como HTTP y JSON, lo que facilita la interoperabilidad con diferentes sistemas y tecnologías. Esto significa que el sistema de la factoría inteligente puede comunicarse y compartir datos de manera efectiva con otros sistemas externos, como sistemas de gestión de inventario, servicios en la nube u otros sistemas de la empresa.
* Good, because Simplificación de la comunicación: REST proporciona una interfaz uniforme y basada en recursos que simplifica la comunicación entre los diferentes componentes del sistema. Los componentes pueden interactuar a través de operaciones HTTP estándar, como GET, POST, PUT y DELETE, utilizando URLs bien definidas para acceder y manipular recursos. Esto facilita la comprensión y el desarrollo de la lógica de comunicación entre los componentes del sistema
* Bad, because Comunicación síncrona: REST se basa en una comunicación síncrona mediante el intercambio de solicitudes y respuestas entre el cliente y el servidor. En un entorno de factoría inteligente con múltiples sensores y componentes que generan eventos en tiempo real, la comunicación síncrona puede no ser eficiente ni escalable. La necesidad de una respuesta inmediata para cada solicitud puede generar cuellos de botella y afectar la capacidad de respuesta del sistema.
* Bad, because Notificaciones en tiempo real: REST no es inherentemente adecuado para proporcionar notificaciones en tiempo real. Si se requiere que los operarios de la factoría sean notificados instantáneamente sobre eventos críticos, como fallos en los sensores o sobrecarga en la producción, puede ser necesario establecer conexiones persistentes o utilizar mecanismos de polling frecuente, lo que puede ser ineficiente y aumentar la carga en el sistema.
* Bad, because Acoplamiento entre componentes: En una arquitectura REST, los componentes suelen estar acoplados a las URLs y estructuras de recursos específicas. Esto puede llevar a una mayor dependencia entre los componentes y dificultar la evolución y actualización individual de cada uno. En un entorno de factoría inteligente, donde la adaptabilidad y la flexibilidad son fundamentales, puede ser beneficioso tener una arquitectura más desacoplada y modular.
* Bad, because Complejidad en la gestión de estados: REST es una arquitectura sin estado, lo que significa que cada solicitud se considera independiente y no almacena información de estado en el servidor. En un sistema en el que se requiere mantener y gestionar el estado de la producción, las órdenes de trabajo y el inventario, el enfoque sin estado de REST puede requerir soluciones adicionales para mantener y sincronizar los estados, lo que puede aumentar la complejidad del sistema.
* Bad, because Escalabilidad en eventos y streaming de datos: Si el sistema de la factoría inteligente genera y procesa grandes volúmenes de eventos o datos en streaming, REST puede no ser la mejor opción. La comunicación basada en solicitudes y respuestas individuales puede ser ineficiente y no escalable en este contexto. Se pueden requerir enfoques más especializados, como arquitecturas basadas en eventos o streaming, para manejar eficientemente este tipo de casos de uso