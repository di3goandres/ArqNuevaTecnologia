# Patron alertas y suscripciones

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-20

## Context and Problem Statement

Generación de alertas: Existen eventos o condiciones específicas que pueden desencadenar una alerta, como actualizaciones de producción, fallos en los sensores IoT, sobrecarga en la producción u otras situaciones críticas. Estas alertas se deben generar automáticamente cuando se detecta una condición predefinida o cuando ocurre un evento relevante.

Suscripción a alertas: Los operarios deben tener la capacidad de suscribirse a las alertas que les resulten relevantes para su trabajo. Pueden seleccionar los tipos de eventos o condiciones específicas a los que desean estar atentos y recibir notificaciones correspondientes.

Sistema de mensajería interno: Para enviar las alertas y notificaciones, se debe implementar un sistema de mensajería interno que permita la comunicación entre el sistema de generación de alertas y los operarios. Este sistema debe ser confiable en cuanto a la entrega de mensajes y garantizar que las notificaciones lleguen a los destinatarios adecuados.

Gestión de suscripciones: Se debe implementar un mecanismo que permita a los operarios administrar sus suscripciones a las alertas. Pueden seleccionar las notificaciones a las que desean suscribirse, configurar preferencias de entrega (por ejemplo, correo electrónico, aplicación móvil, mensajes de texto, etc.) y tener la capacidad de modificar o cancelar sus suscripciones en cualquier momento.

Personalización de alertas: Idealmente, el sistema debe permitir cierto grado de personalización de las alertas para adaptarse a las necesidades individuales de los operarios. Pueden configurar ciertos criterios o condiciones específicas para recibir alertas personalizadas según su rol, ubicación o preferencias.

Registro y seguimiento de alertas: Es importante mantener un registro de todas las alertas generadas y enviadas, incluyendo información relevante como la fecha y hora, el tipo de alerta y los destinatarios. Esto permite un seguimiento y análisis posterior de las alertas para evaluar su eficacia y tomar medidas correctivas si es necesario.

## Decision Drivers

* RF-004	Mensajería y suscripción a eventos
* RF-007	Generación de alertas y notificaciones
* RF-008	Configuración de preferencias y suscripciones a eventos
* RF-0011	Sistema de mensajería Interna

## Considered Options

* Observer

## Decision Outcome

Chosen option: "Publish / Subscriber", because Manera más eficiente para comunicar con los dispositivos receptores.
Flexibilidad en el manejo de suscripciones.

### Positive Consequences

* Desacoplamiento:
* Escalabilidad/ Flexibilidad
* Distribución de Mensajes
* Extensibilidad
* Distribuido
* Los publicadodores no conocen ni dependen de los suscriptores
* Los suscriptores se suscriben a ciertos tipos de eventos o canales de comunicación

### Negative Consequences

* Perdida de mensajes
* Manejo de colas

## Pros and Cons of the Options

### Publish / Subscriber

Nos ayuda a manejar el tema de suscriptores, ya que los mensajes deben ser enviados a estos.

* Good, because Permite comunicación asíncrona
* Good, because Se puede recibir notificaciones cuando se producen alertas
* Good, because Múltiples destinatarios
* Good, because Desacoplada
* Good, because Escalable
* Bad, because Perdida de mensajes: si no hay suscriptores disponibles en el momento de la publicación.
* Bad, because Sobrecarga de mensajes.
