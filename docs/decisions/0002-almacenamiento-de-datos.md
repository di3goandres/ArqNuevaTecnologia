# Almacenamiento de datos

* Status: proposed
* Deciders: Julian Luna, Diego Montealegre
* Date: 2023-06-17

## Context and Problem Statement

Se requiere almacenar los diferentes tipo de datos que recibimos desde los dispositivos IoT.

## Decision Drivers

* RF-0011 Almacenamiento de datos

## Considered Options

* SQL
* NoSQL

## Decision Outcome

Chosen option: "NoSQL", because Escalabilidad y rendimiento: Las bases de datos NoSQL están diseñadas para escalar horizontalmente, lo que significa que pueden manejar grandes volúmenes de datos y cargas de trabajo distribuidas. Esto las hace ideales para aplicaciones que requieren una alta escalabilidad y un rendimiento rápido en entornos de alta demanda.

Flexibilidad del esquema: Las bases de datos NoSQL permiten una mayor flexibilidad en el esquema de los datos. No requieren un esquema predefinido y rígido, lo que facilita los cambios en la estructura de los datos sin interrumpir la aplicación. Esto es especialmente útil en situaciones en las que los requisitos y la estructura de los datos evolucionan con el tiempo.

Datos no estructurados o semiestructurados: Si el sistema maneja principalmente datos no estructurados o semiestructurados, como documentos JSON o XML, una base de datos NoSQL orientada a documentos puede ser más adecuada. Estas bases de datos permiten almacenar y consultar datos complejos sin requerir una estructura fija.

Agilidad en el desarrollo: Las bases de datos NoSQL ofrecen un modelo de desarrollo más ágil, lo que permite una iteración rápida y flexible. No requieren un riguroso diseño de esquema y permiten una mayor velocidad en el desarrollo y la implementación de nuevas características.

Escenarios de uso específicos: Algunos escenarios, como aplicaciones en tiempo real, análisis de big data, almacenamiento de datos en caché o sistemas de gestión de contenido, pueden beneficiarse de las características específicas de las bases de datos NoSQL, como la velocidad de escritura y lectura, la capacidad de almacenar grandes cantidades de datos o el soporte para operaciones distribuidas.

### Positive Consequences

* Escalabilidad horizontal: Las bases de datos NoSQL están diseñadas para escalar horizontalmente, lo que les permite manejar grandes volúmenes de datos y cargas de trabajo distribuidas de manera más eficiente que las bases de datos SQL tradicionales.
* Flexibilidad del esquema: Las bases de datos NoSQL no requieren un esquema predefinido y rígido, lo que permite una mayor flexibilidad en la estructura de los datos. Esto es beneficioso en entornos donde los requisitos y la estructura de los datos pueden cambiar con el tiempo.
* Rendimiento rápido: Debido a su diseño orientado a la eficiencia y la escalabilidad, las bases de datos NoSQL pueden ofrecer un rendimiento más rápido para operaciones de escritura y lectura en comparación con las bases de datos SQL tradicionales, especialmente en entornos de alta carga de trabajo.
* Soporte para datos no estructurados: Las bases de datos NoSQL son especialmente adecuadas para manejar datos no estructurados o semiestructurados, como documentos JSON o XML. Permiten almacenar y consultar este tipo de datos de manera más flexible y eficiente.

### Negative Consequences

* Menor soporte para consultas complejas: En general, las bases de datos NoSQL ofrecen un conjunto de características de consulta más limitado en comparación con las bases de datos SQL tradicionales. Realizar consultas complejas o realizar operaciones de agregación avanzadas puede ser más difícil o requerir enfoques alternativos.
* Menor madurez y menos herramientas: En comparación con las bases de datos SQL, las bases de datos NoSQL suelen tener una menor madurez y una comunidad de desarrollo más joven. Esto puede traducirse en una menor disponibilidad de herramientas, menor documentación y menos experiencia general en el uso de estas bases de datos.
* Menos soporte para transacciones ACID: Algunas bases de datos NoSQL no ofrecen soporte completo para transacciones ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad), lo que puede ser un inconveniente en aplicaciones donde la integridad de los datos y la consistencia estricta son críticas.
* Curva de aprendizaje: La adopción de bases de datos NoSQL puede requerir una curva de aprendizaje adicional para los desarrolladores y administradores del sistema, especialmente si están acostumbrados a trabajar con bases de datos SQL tradicionales.

## Pros and Cons of the Options

### SQL

* Good, because Esquema estructurado: Las bases de datos SQL siguen un modelo de datos estructurado con tablas, filas y columnas definidas previamente. Esto proporciona una estructura clara y definida para los datos, lo que facilita las consultas y la integridad de los datos
* Good, because Transacciones ACID: Las bases de datos SQL son conocidas por su soporte de transacciones ACID (Atomicidad, Consistencia, Aislamiento, Durabilidad), lo que garantiza que las operaciones sean seguras y confiables. Esto es importante en aplicaciones que requieren una alta integridad de los datos y cumplimiento de requisitos de consistencia.
* Good, because Consultas complejas: Las bases de datos SQL ofrecen un poderoso lenguaje de consulta (SQL) que permite realizar consultas complejas y realizar agregaciones avanzadas de datos. Esto es beneficioso cuando se necesitan realizar consultas ad hoc o análisis sofisticados sobre los datos almacenados
* Bad, because Escalabilidad vertical: Las bases de datos SQL tradicionales suelen tener una escalabilidad vertical limitada, lo que significa que es necesario aumentar los recursos de hardware (como CPU y RAM) para manejar una mayor carga de trabajo. Esto puede ser costoso y puede tener limitaciones en términos de escalabilidad y rendimiento.
* Bad, because Flexibilidad del esquema: Las bases de datos SQL requieren un esquema predefinido y rígido, lo que dificulta los cambios en la estructura de los datos. Si se requiere una alta flexibilidad para agregar o modificar campos o estructuras de datos, puede resultar complicado en una base de datos SQL

### NoSQL

* Good, because Flexibilidad del esquema: Las bases de datos NoSQL permiten una mayor flexibilidad en el esquema de los datos. Pueden manejar datos no estructurados, semi estructurados o estructurados de manera más flexible, lo que facilita cambios en el esquema sin interrumpir la aplicación.
* Good, because Escalabilidad horizontal: Las bases de datos NoSQL están diseñadas para ser altamente escalables horizontalmente, lo que significa que pueden manejar grandes volúmenes de datos y cargas de trabajo distribuidas al agregar más nodos de almacenamiento. Esto permite un mejor rendimiento y escalabilidad para sistemas de gran escala
* Bad, because Menos soporte para consultas complejas: En general, las bases de datos NoSQL no ofrecen el mismo nivel de soporte para consultas complejas como las bases de datos SQL. Algunos tipos de bases de datos NoSQL pueden tener un lenguaje de consulta limitado o carecer de características avanzadas de consulta.
* Bad, because Ausencia de transacciones ACID: Algunas bases de datos NoSQL no ofrecen soporte completo para transacciones ACID. Si la integridad de los datos y la consistencia estricta son críticas para la aplicación, esto puede ser una limitación