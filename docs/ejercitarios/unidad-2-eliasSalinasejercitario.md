# Respuestas — Ejercitario Unidad 02

---

## Tema 1 · La naturaleza del software

**1. En tus propias palabras, explica por qué se dice que el software es un producto de "naturaleza particular" en comparación con un producto físico. Menciona al menos tres características distintivas.**

*Respuesta:* El software tiene una naturaleza particular porque es un elemento lógico y no físico. Sus tres características principales son:
1. **No se fabrica, se desarrolla (ingeniería):** No pasa por una cadena de montaje física; su calidad depende del diseño y la lógica.
2. **No se desgasta:** A diferencia de una máquina que se oxida o rompe por fricción, el software no sufre desgaste físico por el uso continuo.
3. **Es altamente maleable:** Se espera que el software pueda modificarse, actualizarse y adaptarse constantemente a nuevos requisitos, algo mucho más difícil de hacer con un puente o un automóvil ya construido.

**2. ¿Por qué se afirma que la calidad del software se degrada por mal mantenimiento y no por el paso del tiempo? Da un ejemplo.**

*Respuesta:* Como el software no sufre desgaste físico, el tiempo en sí no lo daña. Lo que degrada su calidad son los cambios constantes (parches, nuevas funciones, correcciones rápidas) hechos sin cuidar la arquitectura original, lo que genera "deuda técnica". 
**Ejemplo:** Un sistema de facturación antiguo al que se le han agregado decenas de reglas de impuestos nuevas durante años mediante "parches rápidos". El código se vuelve tan enredado y complejo que, eventualmente, arreglar un error pequeño termina rompiendo otra parte del sistema.

---

## Tema 2 · Requisitos funcionales y no funcionales

**3. Explica con tus propias palabras la diferencia entre un requisito funcional y un requisito no funcional.**

*Respuesta:* 
*   **Funcional:** Define *qué* debe hacer el sistema. Son las acciones, comportamientos o funciones específicas (ej. "El sistema debe procesar pagos").
*   **No funcional:** Define *cómo* de bien debe hacerlo el sistema. Son las cualidades, restricciones o atributos de calidad (ej. "El sistema debe procesar los pagos en menos de 2 segundos" o "debe ser seguro").

**4. Para el siguiente caso, identifica un requisito funcional y tres requisitos no funcionales de categorías distintas: "Una aplicación de delivery de comida debe permitir a los usuarios rastrear su pedido en tiempo real."**

*Respuesta:* 
*   **Requisito Funcional:** El sistema debe mostrar en un mapa la ubicación GPS del repartidor asignado al pedido.
*   **Requisito No Funcional 1 (Rendimiento):** La ubicación GPS del repartidor debe actualizarse en la pantalla del usuario cada 5 segundos.
*   **Requisito No Funcional 2 (Usabilidad):** El mapa de rastreo debe poder visualizarse correctamente sin necesidad de hacer zoom en pantallas de teléfonos móviles de 5 pulgadas o más.
*   **Requisito No Funcional 3 (Seguridad):** Solo el cliente que realizó el pedido y el soporte técnico deben tener permiso para ver la ubicación del repartidor.

**5. Menciona dos razones por las cuales los requisitos no funcionales suelen entrar en conflicto entre sí. Da un ejemplo concreto de ese conflicto.**

*Respuesta:* Entran en conflicto porque mejorar un atributo de calidad suele requerir sacrificar recursos que benefician a otro, y porque persiguen objetivos opuestos.
**Ejemplo:** **Seguridad vs. Rendimiento/Usabilidad.** Si se exige que una aplicación médica encripte todos los datos con algoritmos muy complejos y pida autenticación en dos pasos cada 5 minutos (alta seguridad), el sistema se volverá más lento (bajo rendimiento) y muy frustrante para el médico que lo usa (baja usabilidad).

---

## Tema 3 · Clasificación de las cualidades del software

**6. Completa el siguiente cuadro clasificando cada elemento como cualidad "de producto" o "de proceso", y justifica brevemente tu respuesta.**

| Elemento | ¿Producto o proceso? | Justificación |
| --- | --- | --- |
| Tiempo de respuesta de una aplicación móvil | **Producto** | Es un atributo observable del software final una vez que está funcionando. |
| Capacidad del equipo de estimar correctamente los plazos de entrega | **Proceso** | Se refiere a cómo trabaja el equipo de desarrollo y sus metodologías, no al software en sí. |
| Facilidad de uso de una interfaz | **Producto** | Es una característica inherente al diseño de la aplicación entregada al usuario. |
| Documentación interna del código fuente | **Producto (Interno)** | Es un artefacto tangible generado durante la creación del software que afecta su mantenibilidad. |

**7. ¿Por qué se dice que una buena calidad interna favorece, pero no garantiza, una buena calidad externa? Da un ejemplo de un software con buena calidad interna pero mala calidad externa, o viceversa.**

*Respuesta:* La calidad interna (código limpio, buena arquitectura) hace que el software sea fácil de mantener y evolucionar para los desarrolladores. Sin embargo, el usuario final solo percibe la calidad externa (qué tan útil o fácil es).
**Ejemplo:** Un equipo puede programar una aplicación de calculadora con un código impecable, patrones de diseño perfectos y sin un solo bug (excelente calidad interna). Pero si los botones en la pantalla son diminutos y los números son difíciles de leer, el usuario pensará que es una pésima aplicación (mala calidad externa).

---

## Tema 4 · Cualidades representativas

Relaciona cada cualidad con su definición correspondiente.

| Cualidad | N.º de definición |
| --- | --- |
| A. Corrección | **3** |
| B. Fiabilidad | **6** |
| C. Robustez | **4** |
| D. Eficiencia | **2** |
| E. Mantenibilidad | **5** |
| F. Interoperabilidad | **1** |

**8. Elige dos cualidades representativas distintas a las de la actividad anterior (por ejemplo, usabilidad, portabilidad o reusabilidad) y da un ejemplo concreto —de una app, sistema o servicio real— donde esa cualidad sea especialmente crítica.**

*Respuesta:* 
1. **Seguridad:** Crítica en una aplicación bancaria móvil. Si la seguridad falla, se exponen datos financieros y dinero de los usuarios, lo que podría quebrar al banco.
2. **Usabilidad:** Crítica en una aplicación de emergencias médicas o de bomberos. Bajo situaciones de alto estrés, la interfaz debe ser tan intuitiva que el usuario no necesite pensar para apretar el botón correcto.

**9. Caso breve: un equipo de desarrollo debe elegir entre optimizar la eficiencia de un sistema (tiempos de respuesta más rápidos) o su mantenibilidad (código más simple y modular), dado que el tiempo de desarrollo es limitado. ¿Qué factores debería considerar el equipo para tomar esa decisión?**

*Respuesta:* El equipo debe considerar el **dominio de aplicación** y el **ciclo de vida esperado** del software. Si es un sistema donde la velocidad es crítica (como un videojuego o un sistema de frenos ABS), deben priorizar la eficiencia. Si es un sistema empresarial de gestión (como un sistema contable) que se usará durante 10 años y requerirá cambios de reglas constantes, deben priorizar la mantenibilidad para que los costos a futuro no se disparen.

---

## Tema 5 · Calidad según el dominio de aplicación

**10. Completa el siguiente cuadro indicando qué cualidades consideras prioritarias para cada tipo de sistema, y por qué.**

| Tipo de sistema | Cualidades prioritarias | ¿Por qué? |
| --- | --- | --- |
| Sistema de control de una planta industrial | **Robustez, Fiabilidad y Seguridad (Safety)** | Un fallo no controlado podría provocar accidentes físicos, paradas de producción millonarias o daños ambientales graves. |
| Red social de uso masivo | **Escalabilidad, Disponibilidad y Usabilidad** | Debe soportar millones de usuarios concurrentes sin caerse, y ser tan fácil de usar que cualquiera pueda registrarse. |
| Sistema de trading financiero de alta frecuencia | **Eficiencia (latencia mínima) y Corrección** | Un retraso de milisegundos o un cálculo matemático erróneo puede significar la pérdida de millones de dólares. |

**11. En tu opinión, ¿es válido que un sistema de consumo masivo tolere una tasa de fallos mayor que un sistema crítico, a cambio de salir antes al mercado? Justifica tu postura.**

*Respuesta:* Sí, es válido. En aplicaciones de consumo (como un juego de celular o una nueva app de fotos), salir rápido al mercado permite validar si a los usuarios les interesa el producto (concepto de Producto Mínimo Viable). Un fallo allí solo causa molestia temporal. En cambio, en un sistema crítico (software de aviación, equipos médicos), un fallo cuesta vidas, por lo que nunca es aceptable sacrificar la corrección por velocidad de mercado.

---

## Tema 6 · Medición de la calidad del software

**12. Explica con tus propias palabras por qué se dice que una métrica es "un indicador indirecto de la cualidad, y no la cualidad en sí misma".**

*Respuesta:* Porque las cualidades (como la "mantenibilidad" o "usabilidad") son conceptos abstractos que no se pueden medir con una regla matemática exacta. Por lo tanto, medimos atributos concretos (como "cantidad de líneas de código" o "tiempo que tarda el usuario en encontrar un botón") y usamos esos números para *inferir* si la cualidad abstracta es buena o mala.

**13. Menciona un riesgo concreto de que un equipo se enfoque en mejorar una métrica de calidad (por ejemplo, bajar la complejidad ciclomática) sin revisar si la cualidad real mejoró.**

*Respuesta:* El riesgo es que los desarrolladores manipulen el sistema para cumplir la métrica (Ley de Goodhart). Por ejemplo, si se les mide por "escribir funciones con menos de 20 líneas de código", podrían empezar a dividir el código de forma absurda e ilógica solo para cumplir la regla, lo que en realidad hará que el sistema sea *más difícil* de entender (empeorando la mantenibilidad real).

**14. Reflexión final: de todo lo visto en la Unidad 2 (naturaleza del software, requisitos no funcionales, clasificación de cualidades, cualidades representativas, calidad según el dominio, medición), ¿qué idea te resultó más relevante y por qué?**

*Respuesta:* La idea más relevante es que "no existe el software perfecto". En la ingeniería de software todo se trata de equilibrar balanzas (trade-offs). Entender que mejorar la seguridad puede empeorar el rendimiento, o que los requisitos cambian según si hacemos un marcapasos o una red social, demuestra que desarrollar software requiere tanto de decisiones estratégicas como de habilidades técnicas.