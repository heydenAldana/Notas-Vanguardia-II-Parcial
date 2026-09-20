# Guía de estudio: Arquitectura de Aplicaciones de Vanguardia - II Parcial
Esta guía pretender cubrir de forma más compacta todos los contenidos vistos en las 200+ diapositivas en varias presentaciones juntas en total de forma que se asemeje a un examen teórico como fue el primer parcial. Se enumeran los temas acorde a las diapositivas, formulando las preguntas y respuestas teóricas.

## A. Patrones de diseño

1. **¿Qué son los patrones de diseño, que representan y que ofrecen?**

* Los patrones de diseño son soluciones generales y reutilizables para problemas comunes al desarrollar Software.
* Representan las mejores prácticas y experiencias acumuladas por desarrolladores a lo largo del tiempo.
* Ofrecen guías y plantillas para ayudar a los esarrolladores a resolver problemas de diseño de forma eficiente y efectiva, en lugar de dar soluciones únicas para problemas específicos.

---

2. **¿De cuales elementos consta los patrones de diseño?**

* Consta de elementos clave como clases y objetos, así como las relaciones y colaboraciones entre ellos, y son independientes del lenguaje de programación y el contexto específico de la aplicacion, haciendo que se pueda aplicr en una variedad de situaciones.

---

3. **¿Cuales son los 4 beneficios de los patrones de diseño? Explique cada uno**

    1. **Reutilización del código**: los patrones dan soluciones probadas que se pueden aplicar en varios contextos, permitiendo reutilizar código.
    2. **Escalabilidad**: Dan una base sólida para el diseño , lo que facilita la expansión y mantenimiento a medida que el proyecto crece.
    3. **Mantenimiento simplificado**: Al seguir los patrones de diseño, se mejora la estructura dl código, haciendolo mantenible y comprensible el software a lo largo del tiempo.
    4. **Comunicación efectiva**: Los desarrolladores que conocen el mismo patrón de diseño pueden entenderse y comunicarse mejor.

---

4. **Explique los eis puntos clave de la importancia de los patrones dd diseño**

    1. **Reutilización de código**: Al ser soluciones probadas, ayudan a los desarrolladores a reutilizar implementaciones exitosas, acelerando el desarrollo y reduciendo los errores
    2. **Mejora d ela mantenibilidad**: Al promover una estructura clara y organizada, los desarrolladores pueden mantener el código y realizar actualizaciones en el software con mayor facilidad y ser menos propensos a errores inesperados a lo largo del tiempo.
    3. **Flexibilidad y adaptabilidad**: los patrones de diseño permiten crear suliciones que pueden ser flexibles y adaptables a lo largo del tiempo, y destaca cuando las necesidades del software cambian o evolucionan con el tiempo.
    4. **Comunicación efectiva**: Cuando los desarrolladores conocen y trabajan el mismo patrón, comunicarse entre miembros es más fácil y todos entienden la estructura y el diseño del software
    5. **Escalabilidad**: Proporcionan una base sólida para crear software, permitiendo que se puedan aplicar nuevas funciones o módulos sin afectar negativamente algún otro componente del software.
    6. **Eficiencia en el desarrollo**: Los desarrolladores ahorran tiempo en reinventar la rueda con los patrones de diseño ya que se aplican soluciones conocidas a problemas ya conocidos.

---


5. **Resuma en simples palabras la importancia de los patrones de diseño**

* Su importancia radica en su capacidad para mejorar la eficiencia, calidad y mantenibilidad del código, como también proporciona una base sólida para abordar problemas comunes de diseño de forma efectiva.

---

6. **Resuma de forma breve la historia de los patrones de diseño con el paso del tiempo.**

* Todo se remonta a la época de 1970 cuando se da el surgimiento de la programación OOP y el desarrollo de sistemas más compljos. En resumen:
    1. Década de 1970: Durante esta época, se desarrollaron los fundamentos de la programación orientada a objetos. Lenguajes como Simula y Smalltalk sentaron las bases para el diseño de software basado en objetos
    2. Década de 1980: 
        * A mediados de la década, se observó que los desarro  lladores pasaban por problemas comunes en desarrollo de software y se llegaban a soluciones comunes, pero no habia un lenguaje común para describirlos.
        * 1987: Kent Beck y Ward Cunningham escribieron el libro "Smalltalk Best Practice Patterns" donde documentaron soluciones recurrentes a problemas comunes en Smalltalk. No usaron "patroes de diseño" como tal pero sentaron las bases para el concepto.
    3. Década de 1990: 
        * 1994: Erich Gamma, Richard Helm, Ralph Johnson y John Vlissides publicaron el influyente libro "Design Patters: Elements of Reusable Object-Oriented Software" conocido como el "Gang of Four" (GoF). Dicho libro popularizó el término "patrón de diseño" y ya venia con 23 patrones fundamentales. Dicho libro se convirtió en un recurso para desarrolladores estableciendo el lenguaje y la notación para describir patrones de diseño.
    4. Desarrollos posteriores: 
        * Tras el éxito del libro GoF, se comenzaron a documentar más patrones de diseño, así como formarse comunidades y conferencias dedicadas a discutir y desarrollar patrones de diseño. Con el tiempo, se publicaron libros con más patrones de diseño y expanden el conjunto existente. 
        * La comunidad misma ha hecho que los patroes de diseño se adapten a nuevas tecnologpias y paradigmas de programación 
    5. Hoy en día: 
        * Los patrones de diseño siguen siendo una parte integral de la ingenierpia del software, y se han ido adaptando a nuevas tecnologpias y enfoques, como el _desarrollo ágil_ y la _arquitectura de microservicios_. 
        * La comunidad sigue documentando nuevos patrones de diseño y expandiendo los actuales para los desarrolladres del presente.

---

7. **¿Qué son los principios SOLID, y explique cada uno**

* Presentados por Robert C. Marin, son un conjunto de cinco principios de __diseño de software__ que busca dar la aputa a los desarrolladores para crear sistemas más mantenibles, flexibles y escalables y representan un conjunto de buenas prácticas para la programación OOP. 
    1. **Single Respondability Principle**: Una clase debe tener una única responsabilidad. Si tiene más de una razón para cambiar (aka más responsabilidades), se debe considerar dividirla en más clases cumpliendo este principio.
    2. **Open/Closed Principĺe**: Una clase debe estar abierta a su extensión (mediante implementación de interfaces o extensión de clases) PERO cerrada a su modificación.
    3. **Liskov Substitution Principle**: Los objetos de una clase derivada deben poder sustituir a un objeto de clase base sin afectar al programa.
    4. **Interface Segregation Principle**: Una clase no debería implementar interfaces que no utiliza
    5. **Dependency Inversion Principle**: Tanto los módulos de alto y bajo nivel deben depender de abstracciones. Además, dichas abstracciones no deben depender de detalles, sino al revés. Esto fomenta la flexibilidad y facilidad de cambio.

---

8- **Qué son los patrones creacionales y mencione algunos de ellos**

* Son un conjunto de patrones de diseños el cual su enfoque es en la manera en que las instancias de clase y objeto son creadas aborandolo de una manera flexible, eficiente y controlada. Algunos de estos son:
    * Singleton
    * Factory Method
    * Abstract Method
    * Builder
    * Prototype
    * Object Pool
    * Lazy Initialization
    * Dependency Injection
    * Abstract Singleton Factory
    * Multiton

---

9. **Explique el propósito, la estructura y en que aplicaciones se puede ver los patrones creacionales de Singleton, Factory Method y Abstract Method**

|  | Singleton | Factory Method | Abstract Method |
|:---------|:----------|:---------------|:----------------|
| Propósito | Garantiza que solo haya una instancia de esa clase, proporcionanod un punto de acceso global a esa instancia. | Define una interfaz ára crear un objeto, PERO deja que las subclases alteren el tipo de objetos que se crearán |  Proporciona una interfaz para crear familias de objetos relaciones o independendientes sin especificar sus clases concretas. |
| Estructura | Deifne una operación **getInstance()** que permite a los clientes acceder a su única instancia. Además puede contener operaciones únicas que operan en esa instancia. | <ol><li>**Product** define la interfaz del obejto que Factory Method crea</li><li>**ConcreteProduct** implementa la interfaz de este</li><li>**Creator** declara el factory method, que devuelve un objeto de tipo _Product_ </li><li>**ConcreteCreator** implementa este y devuelve una instancia específica de _Concrete Product_</li></ol> | <ol><li>**AbstractFactory** delcara la interfaz para la creación de productos abstractos</li><li>**ConcreteFactory** la implementa para crear prodctos concretos</li><li>**AbstractProduct** delcara la interfaz de un tipo de producto</li><li>**ConcreteProduct** la implementa</li><li>**Client** utiliza las inerfaces declaradas por _AbstractFactory_ y _AbstractProduct_</li></ol> |
| Ejemplos de aplicaciones | Manejo de configuraciones globales, Administradores de recursos compartidos | Frameworks de UI, Librerias de Logging | Interfaces de usuario (UI) y Sistemas de manejo de datos |

---

9. **Explique las ventajas y desventajas de Singleton, Factory Method y Abstract Method**

| Patrón Creacional | Ventajas | Desventajas |
|:------------------|:---------|:------------|
| Singleton | <ul><li>**Accesso Global**: Proporciona un único acceso de punto global a esa instancia, permitiendo la gestión de recursos compartidos y la coordinación en toda la aplicación fácilmente</li><li>**Control sobre instancia única**: Asegura que solo haya una instancia de esa clase, útil para casos como configuraciones globales, administradores de recursos, etc.</li></ul> | <ul><li>**Acoplamiento fuerte**: Puede introducir un acoplamiento fuerte, ya que una sola instancia se vuelve accesible en toda la aplicación</li><li>**Pruebas Unitarias**: Puede dificultar las ruebas unitarias porque el Singleton puede tner efectos secundarios en otras partes del código.</li></ul>|
| Fatory Method | <ul><li>**Flexibilidad**: Hace que la clase padre delegue la responsabilidad de crear objetos a sus subclases, permitiendo flexibilidad a la creación de instancias</li><li>**Desacoplamiento**: Desacopla la implementación de la creción de intancias de la interfaz del producto, permitiendo la variabilidad</li></ul> | <ul><li>**Complejidad adicional**: Puede introducir complejidad al introducir multiples clases e interfaces</li><li>**Número de clases**: a medida que se agregan más productos y creadores, el número de clases puede aumentar considerablemente</li></ul> |
| Abstract Method | <ul><li>**Desacoplamiento**: Permite que el código cliente trabaje con familias de productos sin tener que conocer las clases concretas</li><li>**Escalabilidad**: Facilita la adición de nuevas familias de productos sin modificar el código ciente existente</li></ul> | <ul><li>**Complejidad**: Puede introducir complejidad adicional, especialmente cuando se añaden más productos y fábricas</li><li>**Rigidez en la extensión**: Puede ser complicado agregar nuevos productos a las familias existentes</li></ul> |

---

10. **Indique cuando es útil usar Singleton, Factory Method y Abstract Method**

* Singleton se usa cuando se requiere una única instancia global.
* Factory Method sirve cuando una clase padre NO puede anticipar la clase de objetos que debe crear. Su uso es beneficioso cuando ha múltiples implementaciones de productos y la lógica no da para una simple llamada al constructor.
* Abstract Method se usa cuando se necesita garantizar que los productos de una familia sean compatibles entre sí y s desea evitar que el cliente conozca la clase concreta de los productos.
