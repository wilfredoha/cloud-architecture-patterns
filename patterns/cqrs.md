# CQRS Pattern – Command Query Responsibility Segregation

## 🧩 Descripción

**CQRS** (Command Query Responsibility Segregation) es un patrón arquitectónico que **separa las operaciones de lectura y escritura** de una aplicación. En lugar de usar un único modelo para ambos tipos de operaciones, CQRS divide las responsabilidades en dos modelos distintos:

- **Command Model**: se encarga de las operaciones de escritura (crear, actualizar, eliminar).
- **Query Model**: se encarga de las operaciones de lectura, optimizadas para obtener información rápidamente.

![CQRS Pattern – Command Query Responsibility Segregation](../images/cqrs.png)
---

## ✅ ¿Qué problema soluciona?

### Problemas comunes en modelos tradicionales:
- Un solo modelo de dominio trata de soportar tanto lectura como escritura, lo que genera complejidad innecesaria.
- Dificultad para escalar lectura y escritura de forma independiente.
- Requerimientos conflictivos de consistencia y rendimiento.

### CQRS lo soluciona al:
- Separar el modelo de lectura del de escritura.
- Optimizar cada modelo según su propósito específico.
- Permitir diferentes bases de datos o estructuras según la necesidad de cada operación.

---

## 🎯 Casos de uso

- Sistemas con alto volumen de lectura y escritura, donde se necesita escalado independiente.
- Aplicaciones que requieren vistas personalizadas o proyecciones derivadas.
- Sistemas con reglas de negocio complejas que afectan solo el dominio de escritura.
- Sistemas que implementan **Event Sourcing** o **Materialized Views**.

---

## 🧱 Componentes del patrón

| Componente     | Función                                                                 |
|----------------|-------------------------------------------------------------------------|
| **Command**    | Solicitud para modificar el estado del sistema.                        |
| **Command Handler** | Aplica lógica de negocio y actualiza el estado.                  |
| **Query**      | Solicitud para obtener datos.                                           |
| **Query Handler** | Ejecuta la consulta, usualmente desde un modelo optimizado.        |
| **Read Model** | Base de datos o vista optimizada para lectura.                         |

---

## ⚖️ Beneficios
- Separación clara de responsabilidades.
- Optimización específica de modelos de lectura y escritura.
- Escalabilidad independiente para lectura y escritura.
- Mejora en el rendimiento para consultas complejas.
- Facilita patrones como Event Sourcing y Materialized Views.

---

## ⚠️ Desafíos
- Mayor complejidad en el diseño y mantenimiento.
- Gestión de sincronización entre los modelos (eventual consistency).
- Puede generar duplicación de lógica o datos.
- Más infraestructura (dos modelos, dos bases de datos, más handlers).

---

## 🧠 Relación con otros patrones
- 🔄 CQRS + Materialized View: modelo de lectura actualizado mediante eventos.
- 🧮 CQRS + Event Sourcing: estado del sistema reconstruido desde eventos.
- 📦 Transactional Outbox: garantiza entrega confiable de eventos desde el modelo de comandos.

---

[Menú Principal](https://github.com/wilfredoha/cloud-architecture-patterns)