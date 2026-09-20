# Patrones de Sistemas Distribuidos

1. **Enumere y describa cada uno de los patrones de sistemas distribuidos**

| Patrón | Descripción | Idea central | Dónde se usa | Por qué sirve |
| :--- | :--- | :--- | :--- | :--- |
| **Peer-to-Peer** | Fomenta la comunicación directa entre componentes sin un coordinador central, actuando cada nodo como cliente y servidor. | Modelo descentralizado donde cada nodo interconectado realiza y recibe peticiones. | Sistemas de intercambio de archivos, aplicaciones descentralizadas (DApps) y redes blockchain. | A mayor cantidad de usuarios, mejor fluidez en la transmisión de datos; aporta resiliencia y escalabilidad. |
| **API Gateway** | Punto de entrada unificado para solicitudes de clientes a servicios de backend. | Consolidar las APIs de microservicios en una sola interfaz. | Aplicaciones web modernas y móviles. | Abstrae el backend, centraliza servicios, agrega protección, autenticación y equilibrio de carga. |
| **Pub-Sub (Publish-Subscribe)** | Desacopla productores de mensajes de los consumidores mediante un corredor o bus de eventos. | Un servidor (publicador) categoriza mensajes sin saber quién los leerá. | Sistemas de comunicación masiva en tiempo real. | Desacoplamiento total y escalabilidad masiva al ejecutarse publicadores y suscriptores de forma independiente. |
| **Request-Response** | Comunicación directa donde el cliente envía una solicitud y espera una respuesta del servidor. | El cliente queda esperando mientras el servidor procesa la petición y devuelve el resultado. | Aplicaciones web, APIs RESTful y llamadas RPC entre servicios. | Ofrece un comportamiento predecible y facilita la validación de errores en flujos transaccionales. |
| **Event Sourcing** | Guarda la secuencia de eventos inmutables que llevaron al estado actual en vez de solo el estado actual. | Registrar cada cambio como un evento inmutable para reconstruir el estado. | Finanzas, edición colaborativa y dominios que requieren saber qué pasó y cuándo. | Permite auditoría, consultas históricas y reconstrucción/replay de eventos. |
| **ETL (Extract, Transform, Load)** | Integra datos extraídos de varias fuentes, los transforma y los carga en un destino común. | Extraer, limpiar/convertir y cargar datos a una base o data warehouse. | Migración de datos, BI, reportes y data warehouse. | Automatiza flujos de datos, asegura calidad de datos y soporta procesamiento por lotes. |
| **Batching Pattern** | Acumula datos durante un período o umbral antes de procesarlos como una sola unidad. | Agrupar múltiples operaciones y ejecutarlas de forma conjunta. | Ingestión de datos, procesos ETL y cómputo distribuido. | Reduce el overhead, optimiza la utilización de recursos y disminuye el costo por operación. |
| **Streaming Processing** | Ingestión, procesamiento y análisis continuo de datos en tiempo real. | Trabajar con flujos continuos o potencialmente infinitos de datos. | Finanzas, IoT, monitoreo y ciberseguridad. | Proporciona baja latencia y alto throughput para responder de forma inmediata. |
| **Orchestration Pattern** | Un coordinador central administra la interacción, dependencias y errores entre varios servicios. | Controlar el orden de ejecución entre múltiples sistemas mediante un orquestador. | Automatización de procesos, BPM y orquestación de microservicios (ej. Saga Orchestrator). | Garantiza la ejecución ordenada y coordinada de flujos de trabajo complejos. |

---

2. **Describa las ventajas y desventajas de cada patrón**

| Patrón | Ventajas | Desventajas |
| :--- | :--- | :--- |
| **Peer-to-Peer** | Escalabilidad económica, tolerancia extrema a fallos (sin punto único de falla), baja latencia por cercanía geográfica y resistencia a la censura. | Complejidad de consistencia, vulnerabilidad a nodos maliciosos, desperdicio de ancho de banda por sincronización e incertidumbre de disponibilidad. |
| **API Gateway** | Punto de entrada único, centralización de seguridad, agregación de peticiones y control de tráfico (Rate Limiting). | Punto único de falla, latencia adicional por procesamiento, complejidad de desarrollo y riesgo de acoplar lógica de negocio. |
| **Pub-Sub** | Desacoplamiento total, escalabilidad asíncrona ante picos de tráfico, fácil mantenimiento/extensión y envío a múltiples receptores. | N/A |
| **Request-Response** | Comportamiento predecible y facilita la validación de errores en flujos transaccionales. | N/A |
| **Event Sourcing** | Permite auditoría, consultas históricas y reconstrucción/replay de eventos. | N/A |
| **ETL** | Automatiza flujos de datos, garantiza la calidad y soporta grandes volúmenes por lotes. | N/A |
| **Batching Pattern** | Reduce el overhead, mejora la eficiencia en pipelines y optimiza el uso de recursos. | N/A |
| **Streaming Processing** | Ofrece baja latencia y alto throughput con respuesta casi al instante. | N/A |
| **Orchestration Pattern** | Controla orden de ejecución, dependencias y excepciones para ejecutar flujos complejos. | N/A |

---

3. **¿Cuándo conviene usar Request-Response, Event Sourcing y ETL?**

* **Request-Response:** Conviene usarlo cuando el sistema requiere una **respuesta inmediata**. Sus casos comunes incluyen APIs, inicios de sesión (login), consultas directas y operaciones transaccionales de usuario.
* **Event Sourcing:** Conviene usarlo cuando se necesita **trazabilidad histórica** y saber exactamente qué pasó y cuándo. Sus casos comunes incluyen sistemas de auditoría, finanzas y entornos de edición colaborativa.
* **ETL:** Conviene usarlo para la **integración y consolidación de datos** provenientes de múltiples fuentes. Sus casos comunes incluyen procesos de migración de datos, inteligencia de negocios (BI), generación de reportes y alimentación de data warehouses.
