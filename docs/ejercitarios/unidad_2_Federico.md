# Respuestas — Ejercitario Unidad 02

## Tema 1 · La naturaleza del software

### 1. En tus propias palabras, explica por qué se dice que el software es un producto de "naturaleza particular" en comparación con un producto físico. Menciona al menos tres características distintivas.

**Respuesta:**

El software tiene una naturaleza particular porque no es un objeto físico que pueda tocarse o desgastarse materialmente. Además, una vez desarrollado, puede copiarse y distribuirse a un costo muy bajo. También es un producto flexible, ya que puede modificarse y evolucionar para adaptarse a nuevas necesidades sin necesidad de fabricarlo nuevamente desde cero.

---

### 2. ¿Por qué se afirma que la calidad del software se degrada por mal mantenimiento y no por el paso del tiempo? Da un ejemplo.

**Respuesta:**

La calidad del software no disminuye simplemente porque pase el tiempo, ya que sus componentes no sufren desgaste físico. Sin embargo, puede deteriorarse cuando se realizan cambios sin una planificación adecuada, sin documentación o sin pruebas suficientes. Esto puede introducir errores y aumentar la complejidad del sistema.

**Ejemplo:** un sistema de gestión al que se le agregan nuevas funciones de manera improvisada durante años puede terminar presentando numerosos errores y ser difícil de mantener, aunque inicialmente funcionara correctamente.

---

## Tema 2 · Requisitos funcionales y no funcionales

### 3. Explica con tus propias palabras la diferencia entre un requisito funcional y un requisito no funcional.

**Respuesta:**

Un requisito funcional describe qué debe hacer el sistema, es decir, las funciones o servicios que debe ofrecer. En cambio, un requisito no funcional describe cómo debe comportarse el sistema o qué características de calidad debe cumplir, como seguridad, rendimiento o usabilidad.

---

### 4. Para el siguiente caso, identifica un requisito funcional y tres requisitos no funcionales de categorías distintas: "Una aplicación de delivery de comida debe permitir a los usuarios rastrear su pedido en tiempo real."

**Respuesta:**

**Requisito funcional:**
- El sistema debe permitir al usuario visualizar la ubicación actual de su pedido en tiempo real.

**Requisitos no funcionales:**
- **Rendimiento:** la ubicación del pedido debe actualizarse cada 5 segundos como máximo.
- **Disponibilidad:** el servicio de rastreo debe estar disponible el 99,9 % del tiempo.
- **Usabilidad:** la información de seguimiento debe mostrarse mediante una interfaz clara y fácil de interpretar.

---

### 5. Menciona dos razones por las cuales los requisitos no funcionales suelen entrar en conflicto entre sí. Da un ejemplo concreto de ese conflicto.

**Respuesta:**

1. Los recursos disponibles, como tiempo, presupuesto o capacidad de hardware, son limitados.
2. Mejorar una cualidad puede afectar negativamente a otra.

**Ejemplo:** aumentar la seguridad mediante múltiples factores de autenticación puede disminuir la usabilidad, ya que los usuarios necesitarán completar más pasos para acceder al sistema.

---

## Tema 3 · Clasificación de las cualidades del software

### 6. Completa el siguiente cuadro clasificando cada elemento como cualidad "de producto" o "de proceso", y justifica brevemente tu respuesta.

| Elemento | ¿Producto o proceso? | Justificación |
|-----------|-----------|-----------|
| Tiempo de respuesta de una aplicación móvil | Producto | Es una característica observable del software terminado. |
| Capacidad del equipo de estimar correctamente los plazos de entrega | Proceso | Está relacionada con la forma en que se desarrolla el software. |
| Facilidad de uso de una interfaz | Producto | Es una propiedad percibida directamente por los usuarios. |
| Documentación interna del código fuente | Proceso | Ayuda al desarrollo y mantenimiento del software durante su ciclo de vida. |

---

### 7. ¿Por qué se dice que una buena calidad interna favorece, pero no garantiza, una buena calidad externa? Da un ejemplo de un software con buena calidad interna pero mala calidad externa, o viceversa.

**Respuesta:**

La calidad interna se refiere a aspectos que no son visibles para el usuario, como la organización del código, la documentación y la modularidad. Estos factores ayudan a construir un mejor producto, pero no garantizan que el usuario tenga una buena experiencia o que el sistema satisfaga sus necesidades.

**Ejemplo:** una aplicación puede estar desarrollada con código limpio, bien documentado y fácil de mantener (buena calidad interna), pero tener una interfaz confusa y difícil de usar (mala calidad externa).

---

## Tema 4 · Cualidades representativas

### 7. Relaciona cada cualidad con su definición correspondiente.

| Cualidad | N.º de definición |
|-----------|-----------|
| A. Corrección | 3 |
| B. Fiabilidad | 6 |
| C. Robustez | 4 |
| D. Eficiencia | 2 |
| E. Mantenibilidad | 5 |
| F. Interoperabilidad | 1 |

---

### 8. Elige dos cualidades representativas distintas a las de la actividad anterior (por ejemplo, usabilidad, portabilidad o reusabilidad) y da un ejemplo concreto donde esa cualidad sea especialmente crítica.

**Respuesta:**

**Usabilidad:** en una aplicación bancaria móvil, los usuarios deben poder realizar transferencias y consultar saldos de manera simple y segura. Una mala usabilidad podría provocar errores en operaciones importantes.

**Portabilidad:** un navegador web como Google Chrome debe funcionar correctamente en distintos sistemas operativos como Windows, Linux, macOS y dispositivos móviles.

---

### 9. Caso breve: un equipo de desarrollo debe elegir entre optimizar la eficiencia de un sistema (tiempos de respuesta más rápidos) o su mantenibilidad (código más simple y modular), dado que el tiempo de desarrollo es limitado. ¿Qué factores debería considerar el equipo para tomar esa decisión?

**Respuesta:**

El equipo debería analizar:

- Las necesidades y expectativas de los usuarios.
- La importancia de los tiempos de respuesta para el negocio.
- La frecuencia con la que el sistema será modificado en el futuro.
- El presupuesto y el tiempo disponibles.
- Los costos de mantenimiento a largo plazo.
- El impacto de cada decisión sobre otras cualidades del software.

Si el sistema requiere procesamiento en tiempo real, la eficiencia puede ser prioritaria. Si se espera una evolución constante del producto, la mantenibilidad suele ser más importante.

---

## Tema 5 · Calidad según el dominio de aplicación

### 10. Completa el siguiente cuadro indicando qué cualidades consideras prioritarias para cada tipo de sistema, y por qué.

| Tipo de sistema | Cualidades prioritarias | ¿Por qué? |
|-----------|-----------|-----------|
| Sistema de control de una planta industrial | Fiabilidad, robustez y seguridad | Un fallo puede provocar daños materiales, pérdidas económicas o riesgos para las personas. |
| Red social de uso masivo | Escalabilidad, disponibilidad y usabilidad | Debe atender a millones de usuarios y ofrecer una experiencia fluida. |
| Sistema de trading financiero de alta frecuencia | Eficiencia, fiabilidad y disponibilidad | Retrasos mínimos pueden generar pérdidas económicas significativas. |

---

### 11. En tu opinión, ¿es válido que un sistema de consumo masivo tolere una tasa de fallos mayor que un sistema crítico, a cambio de salir antes al mercado? Justifica tu postura.

**Respuesta:**

Sí, dentro de ciertos límites. En los sistemas de consumo masivo suele ser aceptable lanzar una versión inicial con algunos errores menores que puedan corregirse posteriormente mediante actualizaciones. Sin embargo, esos errores no deben afectar significativamente la experiencia de los usuarios. En los sistemas críticos esta estrategia no es aceptable, ya que los fallos pueden poner en riesgo vidas humanas, generar pérdidas económicas importantes o producir daños materiales.

---

## Tema 6 · Medición de la calidad del software

### 12. Explica con tus propias palabras por qué se dice que una métrica es "un indicador indirecto de la cualidad, y no la cualidad en sí misma".

**Respuesta:**

Una métrica es una medida numérica que intenta reflejar una determinada característica de calidad. Sin embargo, la calidad es un concepto más amplio y complejo que no puede representarse por completo mediante un único valor. Por ello, las métricas sirven como indicadores que ayudan a evaluar la calidad, pero no constituyen la calidad en sí misma.

---

### 13. Menciona un riesgo concreto de que un equipo se enfoque en mejorar una métrica de calidad (por ejemplo, bajar la complejidad ciclomática) sin revisar si la cualidad real mejoró.

**Respuesta:**

Un riesgo es optimizar la métrica sin mejorar realmente el producto. Por ejemplo, un equipo podría dividir una función compleja en muchas funciones pequeñas para reducir la complejidad ciclomática, pero terminar creando un sistema más difícil de comprender y mantener.

---

### 14. Reflexión final: de todo lo visto en la Unidad 2 (naturaleza del software, requisitos no funcionales, clasificación de cualidades, cualidades representativas, calidad según el dominio, medición), ¿qué idea te resultó más relevante y por qué?

**Respuesta:**

La idea que me resultó más relevante es que la calidad del software depende tanto de los requisitos funcionales como de los no funcionales, y que su importancia varía según el dominio de aplicación. No existe un software perfecto para todos los contextos; las prioridades cambian según las necesidades del sistema y de sus usuarios. Comprender esto permite tomar mejores decisiones de diseño y equilibrar adecuadamente cualidades como eficiencia, seguridad, mantenibilidad y usabilidad.
