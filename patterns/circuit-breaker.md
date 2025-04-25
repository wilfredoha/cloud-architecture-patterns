# 🔌 Circuit Breaker Pattern

## 🧩 Descripción

El patrón **Circuit Breaker** se utiliza para **evitar que una aplicación intente ejecutar operaciones que probablemente fallarán**, especialmente cuando se depende de servicios externos o componentes inestables. Funciona como un **fusible eléctrico**: si detecta fallos repetidos, interrumpe las llamadas futuras temporalmente, permitiendo que el sistema se recupere y evitando sobrecarga adicional.

![Circuit Breaker Pattern](../images/Circuit%20Breaker%20Pattern.png)

---

## 🎯 ¿Qué problema soluciona?

- 🧱 Previene que los servicios inestables o caídos afecten a todo el sistema.
- ⚠️ Evita la sobrecarga de recursos al hacer reintentos innecesarios.
- 💥 Rompe la cadena de fallos en arquitecturas de microservicios.
- 🔄 Proporciona una forma automática de **recuperación controlada**.

---

## ⚙️ ¿Cómo funciona?

El circuito tiene tres estados:

| Estado         | Descripción |
|----------------|-------------|
| **Closed**     | Todo funciona normal. Las llamadas se realizan como de costumbre. |
| **Open**       | Se han producido muchos errores. Las llamadas se bloquean automáticamente durante un período de espera. |
| **Half-Open**  | Después del tiempo de espera, se permite una llamada de prueba. Si es exitosa, el circuito se cierra; si falla, vuelve a estado abierto. |

---

✅ Casos de uso
- Comunicación con servicios de terceros (APIs de pago, correo, etc.).
- Llamadas entre microservicios que dependen unos de otros.
- Operaciones costosas en términos de procesamiento o I/O.
- Sistemas donde una caída en cascada podría escalar rápidamente.

---

⚠️ Consideraciones
- Determinar umbrales adecuados de error (ej. 50% de fallos en 20 solicitudes).
- Configurar tiempos de espera realistas entre estados (ej. 30s).
- Monitorear constantemente la tasa de error y el estado del circuito.
- Ideal combinarlo con Retry Pattern.

---

🛠️ Mejores prácticas
- Mantén métricas para el número de errores, estado del circuito, y tiempo de apertura.
- Asegura la idempotencia si usas retry o fallback junto con circuit breaker.
- En sistemas críticos, ofrece respuestas degradadas mientras el servicio está inestable.
- Aplica políticas diferentes según la criticidad del servicio.

---

[Menú Principal](https://github.com/wilfredoha/cloud-architecture-patterns)