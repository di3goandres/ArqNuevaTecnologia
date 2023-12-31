# Almacenamiento de datos

* Status: rejected
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-19

## Context and Problem Statement

Se requiere almacenar los diferentes tipo de datos que recibimos desde los dispositivos IoT.

## Decision Drivers

* RF-009 Almacenamiento de datos

## Considered Options

* NoSQL

## Decision Outcome

Chosen option: "NoSQL"

## Pros and Cons of the Options

### SQL

* Good, because Esquema estructurado: Las bases de datos SQL siguen un modelo de datos estructurado con tablas, filas y columnas definidas previamente. Esto proporciona una estructura clara y definida para los datos, lo que facilita las consultas y la integridad de los datos
* Good, because Transacciones ACID: Las bases de datos SQL son conocidas por su soporte de transacciones ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad), lo que garantiza que las operaciones sean seguras y confiables. Esto es importante en aplicaciones que requieren una alta integridad de los datos y cumplimiento de requisitos de consistencia.
* Good, because Consultas complejas: Las bases de datos SQL ofrecen un poderoso lenguaje de consulta (SQL) que permite realizar consultas complejas y realizar agregaciones avanzadas de datos. Esto es beneficioso cuando se necesitan realizar consultas ad hoc o análisis sofisticados sobre los datos almacenados
* Bad, because Escalabilidad vertical: Las bases de datos SQL tradicionales suelen tener una escalabilidad vertical limitada, lo que significa que es necesario aumentar los recursos de hardware (como CPU y RAM) para manejar una mayor carga de trabajo. Esto puede ser costoso y puede tener limitaciones en términos de escalabilidad y rendimiento.
* Bad, because Flexibilidad del esquema: Las bases de datos SQL requieren un esquema predefinido y rígido, lo que dificulta los cambios en la estructura de los datos. Si se requiere una alta flexibilidad para agregar o modificar campos o estructuras de datos, puede resultar complicado en una base de datos SQL
