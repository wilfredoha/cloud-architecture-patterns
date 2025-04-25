# 🚦 Throttling & Rate Limiting Pattern

## 🧩 Descripción

Los patrones de **Throttling** y **Rate Limiting** se utilizan para **controlar la cantidad de solicitudes** que un cliente o sistema puede realizar en un periodo determinado. Su objetivo principal es **proteger los recursos del sistema** contra sobrecarga, abusos o ataques como DDoS (Denial of Service).

![Throttling & Rate Limiting Pattern](../images/Throttling%20&%20Rate%20Limiting%20Pattern.png)

---

## 🎯 ¿Qué problema soluciona?

- ⚠️ Prevención de la sobrecarga de servicios.
- 🛡️ Protección frente a ataques de denegación de servicio.
- 💸 Control de costos en APIs públicas o servicios en la nube.
- 🔄 Garantizar la calidad de servicio (QoS) para todos los usuarios.
- 📊 Imponer límites a ciertos usuarios o planes tarifarios (freemium, suscripción, etc.).

---

## 🧠 ¿Cómo funciona?

El sistema **rastrea el número de solicitudes** realizadas por un cliente o IP en un intervalo de tiempo determinado y **aplica reglas** para aceptar, retrasar o rechazar nuevas solicitudes.

### Mecanismos comunes

| Estrategia                   | Descripción |
|-----------------------------|-------------|
| Fixed Window                | Permite un número fijo de solicitudes por intervalo de tiempo (por ejemplo, 100 por minuto). |
| Sliding Window              | Combina precisión y eficiencia usando múltiples ventanas superpuestas. |
| Token Bucket                | Los tokens se acumulan con el tiempo, y cada solicitud consume un token. Ideal para ráfagas. |
| Leaky Bucket                | Las solicitudes se procesan a una tasa constante, y el exceso se descarta o se encola. |

---

## ✅ Casos de uso

- APIs públicas (ej. limitar 60 solicitudes por minuto por API key).
- Interfaces de pago o validaciones costosas.
- Servicios de autenticación (evitar ataques de fuerza bruta).
- Interacción entre microservicios para evitar sobrecarga.
- Planes de suscripción con niveles de servicio.

---

## 💡 Buenas prácticas
- Configura límites diferentes para usuarios autenticados vs. anónimos.
- Usa mecanismos de retry-after o backoff exponencial si el cliente excede su límite.
- Aplica rate limiting por IP, por API key o por usuario.
- Monitorea métricas y ajusta los límites dinámicamente según la carga.
- Considera el uso de cuotas mensuales o diarias para modelos de negocio por consumo.

## ⚠️ Desafíos
- Sincronización de contadores en entornos distribuidos (consistencia).
- Balance entre rendimiento y precisión.
- Evitar falsos positivos (usuarios legítimos bloqueados por comportamiento inusual).
- Gestionar ráfagas legítimas (token bucket es preferible a fixed window en estos casos).

---

[Menú Principal](https://github.com/wilfredoha/cloud-architecture-patterns)