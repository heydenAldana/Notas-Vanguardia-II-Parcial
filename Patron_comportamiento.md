# Patrón de Comportamiento

1. **Defina que es un patrón de comportamiento y cuáles hay**

* Estos patrones se ocupan de los algoritmos y de cómo se reparten
responsabilidades entre los objetos, así definen cómo colaboran y se comunican en tiempo de ejecución. Algunos de estos patrones son:
    * Chsin of Responsibility
    * Command
    * Iterator
    * Mediator
    * Memento
    * Observer
    * State
    * Strategy
    * Template Method
    * Visitor

---

2. **Explique el propósito de cada patrón de comportamiento.**

* A continuación se describen de forma breve cada uno:
    * **Chain of Responsibility:** Pasar una solicitud a lo largo de una cadena de manejadores donde cada uno decide si la procesa o la reenvía al siguiente.
    * **Command:** Convertir una solicitud en un objeto independiente con toda su información, permitiendo parametrizar, retrasar, encolar o revertir acciones.
    * **Iterator:** Permitir el recorrido de los elementos de una colección sin exponer su representación interna o estructura subyacente.
    * **Mediator:** Reducir las dependencias caóticas entre objetos restringiendo sus comunicaciones directas y canalizándolas a través de un objeto mediador.
    * **Memento:** Guardar y restaurar el estado previo de un objeto sin revelar los detalles de su implementación o violar su encapsulación.
    * **Observer:** Definir un mecanismo de suscripción para notificar a múltiples objetos sobre cualquier evento o cambio que le suceda al objeto observado.
    * **State:** Permitir que un objeto altere su comportamiento cuando su estado interno cambia, simulando una máquina de estados finitos.
    * **Strategy:** Encapsular distintas variantes de un algoritmo en clases separadas e intercambiables para seleccionarlas dinámicamente en tiempo de ejecución.
    * **Template Method:** Definir el esqueleto fijo de un algoritmo en una clase base, permitiendo que las subclases redefinan o ajusten pasos específicos sin alterar la estructura general.
    * **Visitor:** Separar un algoritmo de la estructura de objetos sobre la que opera, permitiendo agregar nuevas operaciones sin modificar las clases existentes.

---

3. **Describa los problemas y soluciones que hay por cada patrón de comportamiento**

| Patrón | Problema que resuelve | Solución que propone |
| :--- | :--- | :--- |
| **Chain of Responsibility** | Tener múltiples validaciones o condicionales rígidos (`if`) dentro de un mismo método, dificultando su mantenimiento. | Convertir cada validación en un objeto manejador independiente y encadenarlos en secuencia. |
| **Command** | Acoplar la interfaz de usuario con la lógica de negocio, o duplicar código al crear subclases por cada acción. | Extraer la solicitud a una clase Comando con un método `ejecutar()` que conecta emisor y receptor. |
| **Iterator** | Sobrecargar las clases de colección con múltiples algoritmos de recorrido y acoplar el código a su estructura interna. | Extraer el comportamiento de recorrido a objetos independientes llamados iteradores. |
| **Mediator** | Acoplamiento fuerte y comunicaciones caóticas bidireccionales entre múltiples componentes del sistema. | Canalizar toda la interacción a través de un único objeto mediador central que coordine la comunicación. |
| **Memento** | Necesidad de crear un historial para deshacer cambios exponiendo el estado interno o rompiendo la encapsulación. | Delegar la creación e instantánea del estado al propio objeto dueño del estado (Originador). |
| **Observer** | Pérdida de tiempo mediante comprobaciones constantes (polling) o desperdicio de recursos notificando a clases no interesadas. | Implementar un mecanismo de suscripción para notificar eventos automáticamente solo a las clases suscritas. |
| **State** | Clases con bloques masivos de condicionales (`if`/`switch`) para gestionar comportamientos según el estado actual. | Crear clases independientes por cada estado y delegar la ejecución del comportamiento al objeto de estado activo. |
| **Strategy** | Métodos con múltiples algoritmos o cálculos alternativos dentro de bloques condicionales difíciles de extender. | Encapsular cada variante en su propia clase bajo una interfaz común y delegar su ejecución. |
| **Template Method** | Duplicación del flujo o secuencia de pasos en clases similares que solo varían en detalles menores. | Crear una clase base con un método plantilla en orden fijo y dejar que las subclases definan solo los pasos específicos. |
| **Visitor** | Necesidad de añadir operaciones nuevas a una jerarquía de clases existente sin poder o querer modificar su código. | Trasladar la nueva operación a un objeto "visitante" externo y conectar con los elementos mediante un método `accept()`. |

---

4. **Describa las ventajas y desventajas de cada patrón de comportamiento**

| Patrón | Ventajas | Desventajas |
| :--- | :--- | :--- |
| **Chain of Responsibility** | Controla el orden de procesamiento, separa emisor de receptor y permite añadir manejadores sin alterar el código existente. | Una solicitud puede quedar sin procesar si ningún manejador dentro de la cadena la atiende. |
| **Command** | Desacopla quien invoca de quien ejecuta, permite implementar operaciones deshacer/rehacer, encolar o diferir ejecuciones. | Introduce una capa adicional de clases entre emisor y receptor, complicando el diseño. |
| **Iterator** | Cumple con los principios SRP y OCP; permite iteraciones en paralelo y diferir la lectura de elementos. | Puede ser un sobrecoste innecesario en colecciones simples y resultar menos eficiente que un recorrido directo. |
| **Mediator** | Centraliza la comunicación en un solo lugar (SRP), reduce el acoplamiento y facilita la reutilización de componentes. | El mediador puede evolucionar con el tiempo hasta convertirse en un "objeto todopoderoso" (God Object). |
| **Memento** | Genera instantáneas del estado sin romper la encapsulación y simplifica la responsabilidad del originador. | Alto consumo de memoria RAM si se guardan instantáneas con frecuencia o la estructura es compleja. |
| **Observer** | Respeta el principio Abierto/Cerrado (OCP) al añadir suscriptores y permite establecer relaciones dinámicas en ejecución. | No se puede garantizar ni controlar el orden en que los suscriptores reciben las notificaciones. |
| **State** | Elimina condicionales masivos, organiza el código en clases dedicadas (SRP) y facilita añadir nuevos estados (OCP). | Aplicarlo puede resultar una sobrecarga si la máquina de estados tiene pocos estados o transiciones simples. |
| **Strategy** | Permite cambiar algoritmos en tiempo de ejecución, aísla la lógica del negocio de los detalles del cálculo y cumple OCP. | Aumenta el número de clases y los clientes deben conocer las diferencias entre estrategias para elegir la adecuada. |
| **Template Method** | Evita la duplicación de código en algoritmos similares y protege la estructura o secuencia fija del proceso. | Puede limitar la flexibilidad si la estructura del algoritmo cambia mucho, y suele violar el principio LSP en ciertos diseños. |
| **Visitor** | Facilita añadir operaciones sobre clases complejas sin modificarlas (OCP) y reúne comportamientos afines en una clase. | Obliga a actualizar todos los visitantes cada vez que se agrega o elimina una clase de elemento en la jerarquía. |
