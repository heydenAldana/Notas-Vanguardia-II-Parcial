# Patrones de Arquitectura

1. **¿Qué son los patrones de arquitectura?**

* Es una solución general y reutilizable a un problema común en la arquitectura de software dentro de un contexto dado. Son similares a los patrones de diseño de software PERO tienen un diseño más amplio

---

2. **Enumere los tipos de patrones de arquitectura que existen, y explique brevemente que son**

| Patrón de arquitectura | Qué es | Considerar... |
|:-----------------------|:-------|:-------------:|
| Arquitectura Spaguetti | En realidad no es una arquitectura, y se vió en los inicios de las aplicaciones web. | Algunos problemas pueden incluir: Mantenibilidad difícil, dificil de testear, escalabilidad, dificil de entender el código y pueden haber bugs ocultos |
| Arquitectura por Capas | Creada para arreglar el problema de la arquitecura spaguetti. Divide la lógica del programa en capas (Presentación, Lógica de negocio, Acceso a Datos...) | |
| Arquitectura Hexagonal | Aisla las entrads y salidas de la aplicación de la lógica interna de la aplicación. Esto ayuda a que se generen partes independientes que no dependen de los cambios externos, permitiendo ser modificados | |
| Arquitectura MVC | Divide la aplicación en tres partes: </br><ol><li>**Modelo**: Maneja los datos el acceso a la base de datos y la lógica de negocio</li><li>**Vista**: Muestra la información al usuario y recibe la entrada, sin depender del modelo</li><li>**Controlador**: Recibe el input del usuario, actualiza el modelo y decide que vistas mostrar</li></ol>| |
| Arquitectura por Microservicios | Es un estilo de arquitectura que, en las aplicaciones complejas, se divide en un conjunto de servicios pequeños ||
| Arquitectura Monolítica | Todo está integrado en un solo código base (lógica del usuario, frontend, etc.), siguiendo un enfoque tradicional donde la funcionalidad y el despliegue se hacen como una sola unidad ||
| Arquitectura por Canalización | Funciona como un canal o mensaje que es modificado a través de diferentes filtro, obteniwndo un resultado en la salida || 
| Arquitectura basada en el Espacio | Tienen como objetivo monimizar los factores que limitan la escalabilidad de las aplicaciones. Se basa en tener un espacio de memoria distribuido y compartirlo con todos los componentes de la aplicación. ||
