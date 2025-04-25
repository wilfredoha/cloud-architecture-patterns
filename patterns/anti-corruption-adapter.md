# 🛡️ Anti-Corruption Layer (Adapter) Pattern

## 🧩 Descripción

El patrón **Anti-Corruption Layer (ACL)** es un patrón arquitectónico que actúa como una **capa protectora** entre dos sistemas o contextos de dominio diferentes, evitando que las decisiones de diseño o modelos de datos de un sistema afecten negativamente al otro.

Este patrón se basa en la filosofía de **mantener la integridad del dominio propio**, especialmente cuando se debe integrar con un sistema externo o legado cuyo modelo conceptual difiere del nuestro.

![Anti-Corruption Layer (Adapter) Pattern](../images/anti-corruption-layer.png)
---

## 🎯 ¿Qué problema soluciona?

Cuando un sistema moderno necesita interactuar con un sistema legado o de terceros, pueden surgir conflictos por:

- Diferencias en el modelo de datos.
- Reglas de negocio inconsistentes.
- Nombres de campos o estructuras incompatibles.
- Acoplamiento indebido entre contextos.

**El Anti-Corruption Layer actúa como un traductor**, adaptando modelos, estructuras y comportamientos entre los sistemas, **aislando el dominio principal de posibles "contaminaciones"** externas.

---

## 🧠 ¿Cómo funciona?

El ACL se implementa como un conjunto de componentes que **mapean, traducen o adaptan** los datos y comandos entre los sistemas. Esto incluye:

- **Adaptadores** o wrappers que transforman objetos de entrada/salida.
- **Fachadas** que exponen una interfaz propia, desacoplada del sistema externo.
- **Translators/Mappers** para convertir estructuras de datos.

---

## ✅ Casos de uso comunes

- Integración con sistemas legados (ERP, CRM, mainframes).
- Comunicación entre **Bounded Contexts** con modelos distintos en DDD.
- Migración gradual de un monolito hacia microservicios.
- Aislamiento de APIs de terceros con contratos volátiles.

---

## 📦 Beneficios

- 🧼 **Protección del dominio** contra contaminación externa.
- 🔄 **Desacoplamiento** entre sistemas.
- 🔧 **Flexibilidad** para modificar la integración sin impactar el núcleo.
- 🧱 Facilita **migraciones progresivas**.

---

## ⚠️ Desafíos

- Incremento en la complejidad y mantenimiento.
- Puede requerir duplicación de lógica de negocio temporalmente.
- Necesidad de pruebas adicionales entre la ACL y los sistemas externos.

---

[Menú Principal](https://github.com/wilfredoha/cloud-architecture-patterns)