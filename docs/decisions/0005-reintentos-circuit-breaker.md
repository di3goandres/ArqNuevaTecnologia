# Circuit Breaker

* Status: accepted
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-20

## Context and Problem Statement

Se requiere que en caso de error se reintente la conexión entre el dispositivo IoT y el bróker

## Decision Drivers

* RF-004.1 Manejo para el máximo de suscriptores para la mensajería 

## Decision Outcome

Chosen option: "Circuit Breaker"

## Pros and Cons of the Options

### Circuit Breaker

* Good, because Mayor resiliencia: Evita el colapso del sistema y mejora la resiliencia frente a fallos en servicios externos
* Good, because Tiempo de respuesta rápido: Permite respuestas rápidas al bloquear las solicitudes en lugar de esperar tiempos de espera excesivos.
* Good, because Tolerancia a fallos: Proporciona una forma de gestionar y controlar las excepciones y fallos de un servicio externo, evitando la propagación de errores.

## More Information

Driver: Component Circuit Breaker
Libreria: Apiumhub