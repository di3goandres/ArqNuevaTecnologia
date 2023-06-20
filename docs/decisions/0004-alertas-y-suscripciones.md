# Alertas y suscripciones

* Status: proposed
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-17

## Context and Problem Statement

Generación de alertas: Existen eventos o condiciones específicas que pueden desencadenar una alerta, como actualizaciones de producción, fallos en los sensores IoT, sobrecarga en la producción u otras situaciones críticas. Estas alertas se deben generar automáticamente cuando se detecta una condición predefinida o cuando ocurre un evento relevante.

Suscripción a alertas: Los operarios deben tener la capacidad de suscribirse a las alertas que les resulten relevantes para su trabajo. Pueden seleccionar los tipos de eventos o condiciones específicas a los que desean estar atentos y recibir notificaciones correspondientes.

Sistema de mensajería interno: Para enviar las alertas y notificaciones, se debe implementar un sistema de mensajería interno que permita la comunicación entre el sistema de generación de alertas y los operarios. Este sistema debe ser confiable en cuanto a la entrega de mensajes y garantizar que las notificaciones lleguen a los destinatarios adecuados.

Gestión de suscripciones: Se debe implementar un mecanismo que permita a los operarios administrar sus suscripciones a las alertas. Pueden seleccionar las notificaciones a las que desean suscribirse, configurar preferencias de entrega (por ejemplo, correo electrónico, aplicación móvil, mensajes de texto, etc.) y tener la capacidad de modificar o cancelar sus suscripciones en cualquier momento.

Personalización de alertas: Idealmente, el sistema debe permitir cierto grado de personalización de las alertas para adaptarse a las necesidades individuales de los operarios. Pueden configurar ciertos criterios o condiciones específicas para recibir alertas personalizadas según su rol, ubicación o preferencias.

Registro y seguimiento de alertas: Es importante mantener un registro de todas las alertas generadas y enviadas, incluyendo información relevante como la fecha y hora, el tipo de alerta y los destinatarios. Esto permite un seguimiento y análisis posterior de las alertas para evaluar su eficacia y tomar medidas correctivas si es necesario.

## Decision Drivers

* RF-004	Mensajería y suscripción a eventos
* RF-008	Generación de alertas y notificaciones
* RF-0010	Configuración de preferencias y suscripciones a eventos
* RF-0014	Sistema de mensajería Interna

## Considered Options

* Uso de servicios de mensajería en la nube
* sistema de cola de mensajes
* sistema de eventos en tiempo real

## Decision Outcome

Chosen option: "Uso de servicios de mensajería en la nube", because Escalabilidad: Estos servicios están diseñados para manejar altos volúmenes de mensajes y escalan automáticamente según las demandas de carga.

Fiabilidad: Los servicios de mensajería en la nube ofrecen garantías de entrega de mensajes y su infraestructura está diseñada para ser altamente disponible y tolerante a fallos.

Flexibilidad en los canales de entrega: Puedes enviar notificaciones a través de diferentes canales, como correo electrónico, SMS, notificaciones push a aplicaciones móviles, entre otros, lo que permite adaptarse a las preferencias y necesidades de los operarios.

Gestión de suscripciones: Estos servicios proporcionan mecanismos para administrar las suscripciones a los temas o categorías de alertas. Los operarios pueden seleccionar los eventos específicos a los que desean suscribirse y configurar sus preferencias de entrega.

Integración con otros servicios en la nube: Estos servicios suelen estar integrados con otras soluciones en la nube, lo que facilita su implementación y su conexión con otros componentes de tu arquitectura, como bases de datos, sistemas de procesamiento de eventos, entre otros.

### Positive Consequences

* Escalabilidad: Los servicios de nube como SNS ofrecen escalabilidad automática, lo que significa que pueden manejar un alto volumen de mensajes y adaptarse a las demandas de carga sin requerir configuraciones adicionales.
* Alta disponibilidad: Estos servicios están diseñados para ser altamente disponibles, lo que significa que están respaldados por infraestructuras redundantes y tolerantes a fallos. Esto garantiza que las notificaciones puedan ser entregadas de manera confiable incluso en caso de fallas en los componentes subyacentes.
* Facilidad de implementación: La configuración y la integración de SNS en tu arquitectura son relativamente sencillas. La mayoría de los proveedores de servicios en la nube ofrecen documentación completa, SDK y herramientas de desarrollo para facilitar la implementación.
* Amplia gama de canales de entrega: SNS te permite enviar notificaciones a través de múltiples canales, como correo electrónico, SMS, notificaciones push y más. Esto permite adaptarse a las preferencias de los usuarios y garantizar que las notificaciones lleguen de la manera más efectiva posible.
* Administración de suscripciones y permisos: SNS proporciona mecanismos para administrar las suscripciones a los temas de notificación, lo que te permite controlar quién recibe las notificaciones y qué tipo de notificaciones reciben. También puedes administrar los permisos para garantizar la seguridad y la privacidad de las comunicaciones.

### Negative Consequences

* Costo: El uso de servicios en la nube puede generar costos adicionales, especialmente si se envían grandes volúmenes de mensajes o se requieren características avanzadas. Debes evaluar cuidadosamente los precios y considerar el impacto en tu presupuesto.
* Dependencia de la infraestructura de la nube: Al utilizar servicios en la nube, estás confiando en la infraestructura y la disponibilidad del proveedor de servicios. Si el proveedor experimenta interrupciones o problemas de rendimiento, esto puede afectar la entrega de las notificaciones.
* Limitaciones de personalización: Aunque los servicios de notificación en la nube ofrecen una amplia gama de canales de entrega, pueden tener limitaciones en cuanto a la personalización de la apariencia y el formato de las notificaciones. Esto puede afectar la experiencia del usuario final.
* Integración con sistemas existentes: La integración de servicios de nube puede requerir ajustes en tu arquitectura existente, especialmente si ya tienes sistemas de mensajería o notificación en su lugar. Esto puede generar trabajo adicional de desarrollo e implementación.
