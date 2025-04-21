# Load Balancing Pattern

## 🧩 Descripción

El patrón de **Load Balancing** distribuye equitativamente las solicitudes o cargas de trabajo entre múltiples instancias de un componente o servicio, mejorando la escalabilidad, disponibilidad y rendimiento general del sistema.

Este patrón es esencial para sistemas distribuidos donde múltiples nodos deben atender solicitudes concurrentes sin sobrecargar ningún nodo individual.

---

## ✅ Problema que resuelve

- Saturación de recursos en un único servidor o componente.
- Tiempo de respuesta elevado por cuellos de botella.
- Baja disponibilidad en caso de falla de una instancia.
- Escalabilidad limitada.

---

## 🛠️ Implementación común

- **Load Balancers**:
  - AWS ELB (ALB, NLB)
  - NGINX
  - HAProxy
- **Service Discovery**:
  - Consul, Eureka, AWS Cloud Map
- **Client-side Load Balancing**:
  - Ribbon, Spring Cloud LoadBalancer
- **DNS Round Robin** (menos recomendado por falta de salud y control)

---

## 🧪 Ejemplo de Arquitectura

![Load Balancing Architecture](images/load_balancer.jpg)
