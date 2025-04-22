# Execution Orchestrator Pattern for Microservices Architecture

## 🧩 Descripción

El patrón **Execution Orchestrator** se utiliza en arquitecturas de microservicios para coordinar la ejecución de múltiples servicios o pasos de negocio desde un componente central que entiende el flujo completo.

En lugar de que cada servicio invoque al siguiente (como en el patrón de coreografía), en este patrón un **orquestador central** se encarga de llamar explícitamente a cada microservicio en el orden y condiciones definidas.

![Execution Orchestrator Pattern for Microservices Architecture](../images/orchestrator.png)
---

## ✅ ¿Qué problema soluciona y cómo?

### Problemas comunes:
- Lógica de negocio distribuida entre muchos servicios, lo que dificulta la trazabilidad.
- Dificultad para implementar flujos complejos (con decisiones, validaciones, condiciones).
- Baja visibilidad del estado general de un proceso distribuido.

### Solución:
- Centraliza el flujo de ejecución.
- El orquestador controla el orden, las condiciones, los reintentos y el manejo de errores.
- Proporciona trazabilidad y monitoreo de punta a punta.

---

## 🎯 Casos de uso comunes

- Apertura de cuenta bancaria.
- Proceso de onboarding de usuario o cliente.
- Compra en e-commerce (pago, inventario, notificación, envío).
- Procesos de back-office con múltiples validaciones secuenciales.
- Flujos con lógica compleja, condiciones, timeouts y pasos compensatorios.

---

## ☁️ Ejemplo de implementación en la nube

| Servicio        | Plataforma                    |
|-----------------|-------------------------------|
| AWS             | Step Functions, SWF           |
| Azure           | Durable Functions, Logic Apps |
| GCP             | Workflows, Cloud Composer     |
| Genérico        | Camunda, Temporal, Zeebe      |

---

## 📦 Componentes del patrón

- **Orquestador**: Servicio central que define y ejecuta el flujo.
- **Microservicios**: Unidades atómicas de negocio (stateless).
- **Eventos/Resultados**: El orquestador recoge las respuestas y decide el siguiente paso.

---

## ⚠️ Desafíos del Execution Orchestration Pattern
- Punto único de fallo (SPOF)
- Acoplamiento indirecto entre servicios
- Complejidad del orquestador
- Rendimiento y escalabilidad
- Gestión de errores y compensaciones
- Visibilidad vs. Flexibilidad
- Testing y simulación de flujos
- Tiempos de latencia

---

## 🧠 Buenas prácticas
- Mantener el orquestador separado de los servicios (no mezclar lógica).
- Los microservicios deben ser atómicos, idempotentes y desacoplados.
- Implementar métricas y tracing por paso del flujo.
- Preparar estrategias de reintento y compensación (sagas si aplica).
- Usar definiciones declarativas (ej. YAML en Step Functions o Azure Workflows).

---

[Menú Principal](https://github.com/wilfredoha/cloud-architecture-patterns)