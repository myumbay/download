# Cuestionario de Java, JBoss y Oracle

## 1. Fundamentos de Java (POO)

**P: ¿Qué es una clase?**
R: Es una plantilla o molde que define atributos (variables) y comportamientos (métodos) que tendrán los objetos creados a partir de ella. No ocupa memoria hasta que se instancia.

**P: ¿Qué es un objeto?**
R: Es una instancia concreta de una clase, con valores propios para sus atributos, creada en memoria con la palabra clave `new`.

**P: ¿Qué es la encapsulación?**
R: Es el principio de ocultar los atributos internos de una clase (haciéndolos `private`) y exponer su acceso solo a través de métodos públicos (getters/setters), protegiendo así la integridad de los datos.

**P: ¿Qué es la herencia?**
R: Mecanismo por el cual una clase (subclase) hereda atributos y métodos de otra (superclase) usando `extends`, permitiendo reutilizar código.

**P: ¿Qué es el polimorfismo?**
R: Capacidad de un objeto de comportarse de distintas formas según el contexto. Se logra mediante sobrescritura (`@Override`) o sobrecarga de métodos.

**P: ¿Qué es la abstracción?**
R: Consiste en mostrar solo la información esencial de un objeto, ocultando los detalles de implementación. Se logra con clases abstractas e interfaces.

---

## 2. Palabras clave y modificadores en Java

**P: ¿Qué significa `static`?**
R: Indica que un atributo o método pertenece a la clase y no a una instancia específica. Se puede usar sin crear un objeto (ej: `Math.pow()`). Todos los objetos comparten el mismo valor de una variable `static`.

**P: ¿Qué significa `final`?**
R: Depende de dónde se use:
- En una **variable**: su valor no puede cambiar una vez asignado (es una constante).
- En un **método**: no puede ser sobrescrito por una subclase.
- En una **clase**: no puede ser heredada (ej: `String` es `final`).

**P: ¿Qué es un método (a veces llamado "función") en Java?**
R: Es un bloque de código dentro de una clase que realiza una tarea específica. Técnicamente en Java se llama "método" porque siempre pertenece a una clase (Java no tiene funciones sueltas como otros lenguajes).

**P: ¿Qué significa `void`?**
R: Indica que un método no devuelve ningún valor.

**P: ¿Qué es `this`?**
R: Referencia al objeto actual dentro de la propia clase. Se usa para diferenciar atributos de parámetros con el mismo nombre.

**P: ¿Qué es `super`?**
R: Referencia a la superclase (clase padre). Se usa para llamar a su constructor o a métodos sobrescritos.

**P: ¿Qué es `abstract`?**
R: Modificador que indica que una clase o método no tiene implementación completa y debe ser completado por una subclase. Una clase abstracta no se puede instanciar directamente.

**P: ¿Qué es una `interface`?**
R: Es un contrato que define métodos (sin implementación, o con `default`) que las clases deben implementar con `implements`. Permite una forma de herencia múltiple en Java.

**P: Diferencia entre `public`, `private` y `protected`.**
R:
- `public`: accesible desde cualquier clase.
- `private`: accesible solo dentro de la misma clase.
- `protected`: accesible dentro del mismo paquete y por subclases.

**P: ¿Qué es `synchronized`?**
R: Modificador usado en programación concurrente para que solo un hilo (thread) pueda ejecutar ese método o bloque a la vez, evitando condiciones de carrera.

**P: ¿Qué es `volatile`?**
R: Indica que el valor de una variable puede ser modificado por varios hilos, forzando que siempre se lea directamente de memoria principal y no de una copia en caché del hilo.

**P: ¿Qué es `transient`?**
R: Marca un atributo para que sea ignorado durante la serialización de un objeto.

**P: ¿Qué es un constructor?**
R: Método especial con el mismo nombre de la clase, sin tipo de retorno, que se ejecuta al crear un objeto con `new`, usado para inicializar sus atributos.

---

## 3. JBoss (servidor de aplicaciones)

**P: ¿Qué es JBoss?**
R: Es un servidor de aplicaciones Java EE (ahora Jakarta EE) de código abierto, desarrollado por Red Hat. Su versión moderna de código abierto se llama **WildFly**.

**P: ¿Para qué sirve un servidor de aplicaciones como JBoss?**
R: Para desplegar y ejecutar aplicaciones empresariales Java (Servlets, JSP, EJB), gestionando recursos como transacciones, seguridad, conexiones a bases de datos y concurrencia.

**P: ¿Qué formatos de despliegue usa JBoss?**
R:
- **WAR** (Web Application Archive): aplicaciones web.
- **EAR** (Enterprise Application Archive): aplicaciones empresariales completas, que pueden incluir varios WAR y EJB.
- **JAR**: librerías o módulos EJB simples.

**P: ¿Qué es un EJB (Enterprise JavaBean)?**
R: Componente del lado del servidor que encapsula lógica de negocio, gestionado por el contenedor de JBoss, que ofrece servicios como transacciones y seguridad automáticamente.

**P: ¿Qué es JNDI en JBoss?**
R: (Java Naming and Directory Interface) Sistema que permite buscar y acceder a recursos (como conexiones a bases de datos o EJBs) mediante un nombre lógico, sin conocer los detalles de configuración.

**P: ¿Dónde se configuran los recursos como los DataSources en JBoss?**
R: En el archivo `standalone.xml` (o `domain.xml` en modo dominio), dentro de la carpeta `configuration`, o mediante archivos de despliegue `*-ds.xml`.

---

## 4. Oracle (base de datos)

**P: ¿Qué es Oracle Database?**
R: Es un sistema gestor de bases de datos relacional (RDBMS) desarrollado por Oracle Corporation, ampliamente usado en entornos empresariales.

**P: ¿Qué es JDBC?**
R: (Java Database Connectivity) API de Java que permite conectar aplicaciones Java con bases de datos como Oracle, ejecutando sentencias SQL desde el código.

**P: ¿Qué se necesita para conectar Java con Oracle?**
R: El driver JDBC de Oracle (`ojdbc.jar`), la URL de conexión (ej: `jdbc:oracle:thin:@localhost:1521:orcl`), usuario y contraseña.

**P: ¿Qué es PL/SQL?**
R: Es el lenguaje procedural propio de Oracle, una extensión de SQL que permite escribir bloques de código con lógica (variables, condicionales, bucles), procedimientos y funciones almacenadas.

**P: Diferencia entre `Statement` y `PreparedStatement` en JDBC.**
R:
- `Statement`: ejecuta SQL directo, sin parámetros, vulnerable a inyección SQL.
- `PreparedStatement`: permite parámetros (`?`), es precompilado, más eficiente y seguro contra inyección SQL.

**P: ¿Qué es un `ResultSet`?**
R: Objeto que representa el conjunto de resultados devueltos por una consulta SQL, que se recorre fila por fila con `next()`.

**P: ¿Qué es un procedimiento almacenado (stored procedure)?**
R: Bloque de código PL/SQL guardado en la base de datos, que se puede invocar repetidamente desde Java (usando `CallableStatement`), mejorando rendimiento y reutilización.

**P: ¿Cómo se maneja una transacción en JDBC?**
R: Con `connection.setAutoCommit(false)`, ejecutando las operaciones y confirmando con `commit()`, o revirtiendo con `rollback()` si ocurre un error.

---

*Documento de estudio: si necesitas que profundice en algún tema específico (ejemplos de código, colecciones, hilos, más sobre WildFly/JBoss, o consultas SQL avanzadas de Oracle), dime cuál y lo amplío.*
