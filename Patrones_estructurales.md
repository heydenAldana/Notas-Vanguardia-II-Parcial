# Patrones Estructurales

1. **¿Qie son los patrones estructurales?**

* Son los patrones de diseño que esyán relacionados a la forma en que las clases y objetos se componen para crear estructuras más grandes. O sea, describen formas de construir objetos para realizar una nueva funcionalidad.

---

2. **¿Cual es su origen?**

* En 1990 se pública el libro _Design Patterns: Elements of Reusable Object-Oriented Software_, el cual fue escrito con el propósito de proveer soluciones simples y elegantes a problemas específicos en el diseño de sftware orientado a objetos. Contiene un total de 23 patrones de diseño y se divide en tres categorías:
    * Creacionales
    * Estructurales
    * De comportamiento

---

3. **Mencione los patrones estructurales y que son cada uno**

* **ADAPTER**: Permite la colaboración entre objetos con unterfaces incompatibles
* **BRIDGE**: Permite dividir una clase grande, o un grupo de clases estrechamente relacionadas en dos jerarquías separadas (abstracción e implementación) las cuales pueden desarrollarse independietemente una de la otra.
* **COMPOSITE**: Te permite componer objetos en estructuras de árbol y trabajar con esas estructuras como si fueran objetos individuales.
* **DEECORATOR**: Perite añadir funcionalidades a objetos colocando estos objetos dentro de encapsuladores especiales que contienen estas funcionalidades.
* **FACADE**: Proporciona una interfaz simplificada a una biblioteca, un framework o cualquier otro grupo complejo de clases.
* **FLYWEIGHT**: Permite mantener más objetos dentro de la cantidad disponible de RAM compartiendo las partes comunes del estado entre varios objetos en lugar de mantener toda la información en cada objeto.
* **PROXY**: Permite proporcionar un sustituto o marcador de posición para otro objeto, ya que un proxy controla el acceso al objeto original, permitiéndote hacer algo antes o después de que la solicitud llegue al objeto original.

---

4. **Describa el problema que aborda cada patrón estrcutural, su aplicabilidad, sus ventajas y desventajas**
  </br>
_Nota: la tabla fue creada con ayuda de la IA para competarla con la infomración a partir de las diapositivas_
</br>

| Patrón | Problema | Aplicabilidad | Ventajas | Desventajas |
|:---|:---|:---|:---|:---|
| **Adapter** | Colaboración e integración entre objetos o bibliotecas externas con interfaces incompatibles (ej. datos en XML vs. JSON). | - Cuando se quiere usar una clase existente cuya interfaz no sea compatible con el resto del código.<br>- Cuando se quieran reutilizar subclases existentes que carecen de funcionalidad común no añadible a la superclase. | - **Responsabilidad única:** Separa la interfaz o conversión de datos de la lógica de negocio primaria.<br>- **Abierto/Cerrado:** Permite introducir nuevos adaptadores sin romper el código cliente existente. | - Aumenta la complejidad general del código al introducir nuevas clases e interfaces.<br>- A veces resulta más sencillo modificar la clase de servicio original. |
| **Bridge** | Jerarquías de clases que crecen exponencialmente por combinar múltiples dimensiones ortogonales o independientes (ej. Formas y Colores) mediante herencia. | - Al dividir y organizar una clase monolítica con muchas variantes de una sola funcionalidad (ej. varios servidores DB).<br>- Al necesitar extender una clase en varias dimensiones independientes.<br>- Al requerir cambiar implementaciones durante el tiempo de ejecución. | - Crea clases independientes de la plataforma.<br>- El cliente trabaja con abstracciones de alto nivel sin exponerse a detalles de la plataforma.<br>- Permite añadir abstracciones e implementaciones de forma independiente. | - Puede complicar el código si se aplica a una clase que ya es muy cohesionada. |
| **Composite** | Necesidad de calcular o procesar valores agregados en estructuras complejas de objetos compuestos y simples (ej. Cajas que contienen Productos u otras Cajas). | - Cuando se debe implementar una estructura de objetos en forma de árbol.<br>- Cuando el código cliente deba tratar elementos simples y complejos de la misma forma. | - Facilita el trabajo con árboles complejos mediante polimorfismo y recursión.<br>- **Abierto/Cerrado:** Permite añadir nuevos tipos de elementos sin romper el código existente. | - Dificultad para proporcionar una interfaz común a clases con funcionalidades muy dispares, lo que obliga a sobregeneralizar la interfaz. |
| **Decorator** | Limitaciones de la herencia (estática y rígida) para añadir responsabilidades o combinar múltiples comportamientos en tiempo de ejecución (ej. notificaciones por Email, SMS, Slack, Facebook). | - Al requerir asignar funcionalidades adicionales a objetos en tiempo de ejecución sin alterar el código que los usa.<br>- Cuando no es posible o resulta extraño extender el comportamiento usando herencia. | - Extiende comportamientos sin crear subclases.<br>- Añade o elimina responsabilidades en tiempo de ejecución y permite combinar envoltorios.<br>- **Responsabilidad única:** Divide clases monolíticas en clases más pequeñas. | - Dificultad para retirar un wrapper específico de la pila de envoltorios.<br>- Dependencia del orden de colocación en la pila de decoradores.<br>- El código de configuración inicial de capas puede verse complejo o desagradable. |
| **Facade** | Código estrechamente acoplado y difícil de mantener al interactuar directamente con un subsistema, biblioteca o framework complejo de múltiples partes. | - Cuando se requiere una interfaz limitada pero directa a un subsistema complejo.<br>- Al estructurar un subsistema complejo en capas. | - Aisla el código cliente de la complejidad interna de uno o varios subsistemas. | - La fachada corre el riesgo de convertirse en un objeto todopoderoso acoplado a todas las clases de la aplicación. |
| **Flyweight** | Alto consumo de memoria RAM y bajo rendimiento causado por la creación masiva de objetos que contienen datos e información duplicada (estado intrínseco). | - Cuando el programa deba soportar una enorme cantidad de objetos similares que consumen casi toda la RAM disponible y cuyos estados repetidos se pueden compartir. | - Permite mantener un volumen masivo de objetos dentro de la memoria RAM disponible al compartir sus partes comunes. | - [Inferencia] Mayor complejidad técnica al separar el estado intrínseco (compartido) del extrínseco (único) y gestionar su fábrica (*FlyweightFactory*). |
| **Proxy** | Controlar el acceso o diferir la creación de objetos pesados o de terceros sin alterar la clase original ni duplicar código en los clientes. | - **Proxy virtual:** Inicialización diferida de objetos pesados hasta su uso.<br>- **Proxy de protección:** Control de acceso verificando credenciales del cliente.<br>- **Proxy de caché:** Almacenamiento en caché de resultados costosos. | - [Inferencia] Permite realizar acciones antes o después de delegar la solicitud al objeto real, controlando el acceso y optimizando recursos sin modificar el servicio original. | - [Inferencia] Introduce un nivel adicional de indirección, lo que puede aumentar la complejidad y latencia en las llamadas al servicio real. |
