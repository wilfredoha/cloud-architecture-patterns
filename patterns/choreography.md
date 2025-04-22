# Choreography Pattern for Microservices Architecture

## 🧩 Descripción

El patrón **Choreography** se usa para modelar la interacción entre microservicios como una serie de eventos autónomos y reacciones. En lugar de tener un orquestador central que dirige todo el flujo, **cada servicio conoce su rol y actúa en función de eventos recibidos**.

Este patrón encaja perfectamente en sistemas **event-driven**, promoviendo **desacoplamiento** y **escalabilidad**.

![Choreography Pattern for Microservices Architecture](../images/choreography-pattern.png)
---

## ✅ ¿Qué problema soluciona y cómo?

### Problemas comunes:
- Fuerte acoplamiento con orquestadores que se convierten en un "single point of failure".
- Falta de flexibilidad para evolucionar servicios de manera independiente.
- Procesos distribuidos que necesitan ser escalables y resilientes.

### Solución:
- Cada servicio escucha eventos relevantes y emite eventos cuando finaliza su tarea.
- No hay un controlador central del flujo: la lógica está distribuida.
- Se facilita el escalado horizontal y la evolución del sistema.

---

## 🎯 Casos de uso comunes

- Proceso de compra o checkout en e-commerce.
- Flujos de onboarding de usuario o cliente.
- Publicación de contenido y moderación automática.
- Sistemas de facturación o pagos distribuidos.
- Cualquier arquitectura basada en eventos (*event-driven architecture*).

---

## ☁️ Ejemplo técnico en la nube

| Servicio                | Plataforma                     |
|-------------------------|--------------------------------|
| AWS                     | SNS, EventBridge               |
| Azure                   | Event Grid, Service Bus        |
| GCP                     | Pub/Sub                        |
| Open Source             | Apache Kafka, NATS, RabbitMQ   |
| SaaS / BaaS             | Temporal.io, Camunda Zeebe     |

---

## 📦 Componentes del patrón

- **Event Broker**: Canal de eventos que conecta los microservicios.
- **Productores de eventos**: Servicios que publican eventos al terminar una acción.
- **Consumidores de eventos**: Servicios que reaccionan a eventos y ejecutan su parte del flujo.

---