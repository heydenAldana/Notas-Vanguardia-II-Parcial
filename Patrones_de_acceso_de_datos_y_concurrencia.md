# Patrones de Acceso de Datos y Concurrencia

1. **¿Que es un DAO?**

* Un Data Acces Object (DAO) es un objeto que proporciona una interfaz para poder acceder a los datos de una base de datos, siendo responsable del CRUD en la base de datos así como de mapear los resultados a los objetos de negocio.

---

2. **¿Qué es un Repository**

* Es un patrón de diseño y un componente de software que se encarga de gestionar un modelo o tabla en específico de la base de datos como si fuera una colección de objetos en memoria.

---

3. **Compare el DAO y el Repository en sus enfoques, nivel, objetivos y con que trabajan**

|| ENFOQUE | NIVEL | TRABAJA CON | OBKETIVO |
|:-:|:-----|:------|:------------|:---------|
| D.A.O. | Acceso a datos | Registros de datos | Más cercano a la BD | Encapsular persistencia |
| REPOSITORY | Abstracción de una entidad | Entidades | Más cercano al dominio | Abstraer el acceso a la Entidad |

---

4. **Explique que es Unit of Work**

* Es un patrón de diseño de software que agrupa múltiples operaciones y las ejecuta en una sola transacción, asegurando que TODAS se guarden o NINGUNA lo haga.

---

5. **Enumere y explique cada anomalía en la concurrencia**

    1. **Lost Update**: Dos transacciones leen el mismo valor. Entonces la segunda sobreescribe el cambio de la primera, perdiéndose la actuallización.
    2. **Dirty Read**: Una transacción lee los datos de otra transacción que no se ha confirmado y luego se hace rollback.
    3. **Non-Repeatable Read**: Una transacción A lee los datos dos veces y en la segunda lectura los datos ya no son iguales porque otra transacción B modificó y confirmó los valores.

---

6. **¿Que son los patrones de diseño de concurrencia?**

* Según Lopez Alí, son formas de cómo trabajar con tareas concurrentes de forma efectiva.

---

7. **Enumere y explique los patrones de diseño de concurrencia**

    1. **Active Object**: Es una solución para estructurar aplicacione sconcurrentes desacoplando la ejecución de métodos del objeto que los invoca.
    2. **Monitor Object**: Permite coordinar el acceso a un recurso compartido mediante la encapsulación de todas las operaciones sobre el recurso dentro de un único objeto.
    3. **Thread Pool**: Mantiene un conjunto de hilos reutilizables para ejecutar múltiples tareas, evitando el costo de crear y destruir hilos constantemente. Algunas de sus características son:
        - Puede ser fijo o dinámico (se ajsta segpun la carga)
        - Las tareas se colocan en una cola de tareas
        - Los hilos toman las tareas y las ejecutan
        - Reducen el costo de crear y destruir hilos
    4. **Event Loop o Reactor**: Funciona con un ciclo de eventos, es decir, un hilo se queda escuchando eventos como peticiones de red o solicitudes de lectura hasta que recibe un evento, entonces se lo pasa a un handler que lo procesa. Esto permite manejar muchas conexiones sin crear muchos hilos.
    5. **Proactor**: Es un patrón donde se inicia una operación asíncrone (leer un archivo o una petición de red) y el sistema no se queda esperando. Así cuando la operación termina, se ejecuta autoáticamente un manejador que procesa el resultado. Esto hace que los hilos no se bloqueen mientras se espera la respuesta de una tarea.
    6. **Productor y Consumer**: Separa quien produce la información de quien la consume. En lugar de comunicarse directamente, usan una cola compartido, permitiendo que ambos puedan trabajar a su propio ritmo  y el sistema sea más eficiete y organizado.
