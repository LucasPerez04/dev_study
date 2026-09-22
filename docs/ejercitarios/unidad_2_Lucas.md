# GUÍA DE TRABAJO N.º 2
**Software: su naturaleza y sus cualidades**

* **Asignatura:** Ingeniería de Software  
* **Unidad:** 2 — Software: su naturaleza y sus cualidades  
* **Modalidad:** Individual  
* **Duración sugerida:** 45–60 minutos  

---

## TEMA 1 · LA NATURALEZA DEL SOFTWARE

### 1. En tus propias palabras, explica por qué se dice que el software es un producto de “naturaleza particular” en comparación con un producto físico. Menciona al menos tres características distintivas.

Se afirma que el software tiene una **naturaleza particular** porque es un elemento puramente lógico e intangible, a diferencia de los productos físicos que están sujetos a leyes mecánicas y desgaste de materiales. Sus principales características distintivas son:

1. **Inmaterialidad / Intangibilidad:** No se puede tocar ni medir con magnitudes físicas; existe únicamente como lógica computacional almacenada en medios digitales.
2. **Ausencia de desgaste físico:** El software no se rompe, oxida ni desgasta por el uso repetido; las fallas que presenta se deben a errores de diseño o implementación preexistentes.
3. **Mantenimiento por modificación:** A diferencia de los objetos físicos que se reparan cambiando piezas gastadas por repuestos idénticos, el software se "repara" alterando su código interno, lo cual introduce el riesgo de generar nuevos errores no detectados.

---

### 2. ¿Por qué se afirma que la calidad del software se degrada por mal mantenimiento y no por el paso del tiempo? Da un ejemplo.

El software no sufre degradación física con el tiempo. La degradación de su calidad ocurre por un **mal mantenimiento**, es decir, cuando se agregan parches apresurados, se corrigen errores de forma superficial o se añaden nuevas funcionalidades sin respetar la arquitectura original ni actualizar la documentación. Esto incrementa la complejidad del código y genera un fenómeno conocido como "envejecimiento del software".

* **Ejemplo:** Un sistema de facturación diseñado originalmente para una pequeña tienda comienza a recibir parches continuos a lo largo de 5 años para adaptarse a nuevas normativas impositivas y métodos de pago. Si las modificaciones se realizan mediante parches rápidos ("hacks") sin reestructurar el código, el sistema se vuelve inestable, lento y muy difícil de modificar sin romper otras partes, aunque el entorno de hardware siga funcionando intacto.

---

## TEMA 2 · REQUISITOS FUNCIONALES Y NO FUNCIONALES

### 3. Explica con tus propias palabras la diferencia entre un requisito funcional y un requisito no funcional.

* **Requisito Funcional:** Define **qué debe hacer** el sistema. Describe los servicios, comportamientos, acciones directas, entradas y salidas que el software debe ejecutar en respuesta a estímulos específicos de los usuarios o de otros sistemas.
* **Requisito No Funcional:** Define **cómo debe ser** el comportamiento del sistema o bajo qué restricciones debe operar. Especifica propiedades de calidad, atributos del entorno, restricciones tecnolégicas o niveles de rendimiento (seguridad, usabilidad, tiempo de respuesta, disponibilidad, etc.).

---

### 4. Para el siguiente caso, identifica un requisito funcional y tres requisitos no funcionales de categorías distintas:

> *"Una aplicación de delivery de comida debe permitir a los usuarios rastrear su pedido en tiempo real."*

* **Requisito Funcional:**
  * La aplicación debe mostrar en el mapa interactivo la ubicación geográfica actualizada del repartidor mientras la orden esté en estado "En camino".
* **Requisitos No Funcionales:**
  * **Rendimiento (Performance):** La ubicación del repartidor en el mapa debe actualizarse con una latencia no mayor a 3 segundos.
  * **Usabilidad:** La pantalla de rastreo en tiempo real debe ser legible e intuitiva en dispositivos móviles con pantallas desde 4.7 pulgadas.
  * **Disponibilidad / Fiabilidad:** El servicio de rastreo por GPS debe estar operativo el 99.9% del tiempo durante el horario de atención de las cocinas adheridas.

---

### 5. Menciona dos razones por las cuales los requisitos no funcionales suelen entrar en conflicto entre sí. Da un ejemplo concreto de ese conflicto.

Los requisitos no funcionales entran en conflicto principalmente por dos razones:
1. **Competencia por recursos finitos:** La mejora de un atributo de calidad suele requerir más recursos de cómputo, memoria, red o tiempo de desarrollo, perjudicando a otro.
2. **Trade-offs arquitectónicos:** Las técnicas necesarias para maximizar una cualidad (como la seguridad) agregan capas de procesamiento que impactan negativamente en otra cualidad (como la eficiencia o velocidad).

* **Ejemplo concreto:** El conflicto entre **Seguridad** y **Eficiencia / Usabilidad**. Si un sistema bancario exige cifrado extremo de extremo a extremo, autenticación multifactor constante y re-verificación biométrica en cada operación (alta seguridad), esto incrementa los tiempos de respuesta del servidor y dificulta la fluidez de uso para el usuario (menor eficiencia y usabilidad).

---

## TEMA 3 · CLASIFICACIÓN DE LAS CUALIDADES DEL SOFTWARE

### 6. Completa el siguiente cuadro clasificando cada elemento como cualidad “de producto” o “de proceso”, y justifica brevemente tu respuesta.

| Elemento | ¿Producto o proceso? | Justificación |
| :--- | :--- | :--- |
| **Tiempo de respuesta de una aplicación móvil** | **Producto** | Mide el comportamiento directo del software ejecutado durante su uso por parte del usuario final. |
| **Capacidad del equipo de estimar correctamente los plazos de entrega** | **Proceso** | Evalúa la madurez, organización y efectividad de las actividades metodológicas de desarrollo del equipo. |
| **Facilidad de uso de una interfaz** | **Producto** | Es un atributo intrínseco de la interfaz terminada del software (Usabilidad) percibido por el usuario. |
| **Documentación interna del código fuente** | **Producto** | Refleja la calidad interna del artefacto de software generado (Mantenibilidad), facilitando su comprensión futura. |

---

### 7. ¿Por qué se dice que una buena calidad interna favorece, pero no garantiza, una buena calidad externa? Da un ejemplo de un software con buena calidad interna pero mala calidad externa, o viceversa.

Se afirma esto porque la **calidad interna** (estándares de código, arquitectura modular, documentación, patrones de diseño) facilita la construcción del sistema, pero el usuario final solo percibe la **calidad externa** (usabilidad, velocidad, ausencia de errores visibles). Un código impecable puede dar como resultado un producto inútil si no cumple con las verdaderas necesidades del usuario o si su interfaz es confusa.

* **Ejemplo (Buena calidad interna pero mala calidad externa):** Un software de gestión empresarial cuyo código fuente sigue al pie de la letra los mejores patrones de diseño, está 100% probado con tests unitarios y bien documentado, pero su interfaz gráfica es anticuada, requiere 15 clics para realizar una tarea sencilla y el usuario final no comprende las etiquetas de los botones. El producto es técnicamente perfecto internamente, pero externamente es deficiente en usabilidad.

---

## TEMA 4 · CUALIDADES REPRESENTATIVAS

### Relación de Cualidades y Definiciones

| Cualidad | Definición |
| :--- | :--- |
| **A. Corrección** | **3.** El software hace exactamente lo que su especificación indica, ni más ni menos. |
| **B. Fiabilidad** | **6.** Capacidad de funcionar sin fallar durante un período y bajo condiciones dadas. |
| **C. Robustez** | **4.** Comportamiento razonable frente a situaciones no anticipadas por la especificación. |
| **D. Eficiencia** | **2.** Uso adecuado de los recursos disponibles: tiempo de procesamiento, memoria, ancho de banda. |
| **E. Mantenibilidad** | **5.** Facilidad para corregir errores y adaptar o mejorar el software. |
| **F. Interoperabilidad** | **1.** Capacidad de coexistir e intercambiar información con otros sistemas. |

---

### 8. Elige dos cualidades representativas distintas a las de la actividad anterior y da un ejemplo concreto donde esa cualidad sea especialmente crítica.

1. **Portabilidad:**
   * **Ejemplo crítico:** Un navegador web moderno (como Google Chrome o Mozilla Firefox). Debe ejecutarse de manera idéntica en diversos sistemas operativos (Windows, macOS, Linux, Android, iOS) y arquitecturas de procesador (x86, ARM) utilizando la mayor cantidad de código base común para minimizar costos de desarrollo.
2. **Reusabilidad:**
   * **Ejemplo crítico:** Una pasarela de pagos (como Stripe o Mercado Pago SDK). Sus componentes de código (módulos de procesamiento de tarjetas, validación de token de seguridad) deben estar diseñados para integrarse fácilmente en miles de e-commerce completamente distintos sin necesidad de modificar su lógica interna.

---

### 9. Caso breve: un equipo de desarrollo debe elegir entre optimizar la eficiencia de un sistema o su mantenibilidad, dado que el tiempo de desarrollo es limitado. ¿Qué factores debería considerar el equipo para tomar esa decisión?

El equipo debería evaluar los siguientes factores clave:
* **Vida útil estimada del software:** Si el sistema operará durante años y requerirá evoluciones constantes, debe priorizarse la mantenibilidad.
* **Restricciones de hardware y volumen de operaciones:** Si el software corre en dispositivos con recursos limitados (IoT) o maneja millones de transacciones por segundo, la eficiencia es prioritaria.
* **Costo de oportunidad y tiempo de salida al mercado (*Time-to-Market*):** Determinar si un retardo por optimizar código compromete el negocio.
* **Impacto del rendimiento en la experiencia del usuario:** Evaluar si la falta de eficiencia degradaría la usabilidad hasta volver inaceptable el servicio.

---

## TEMA 5 · CALIDAD SEGÚN EL DOMINIO DE APLICACIÓN

### 10. Completa el siguiente cuadro indicando qué cualidades consideras prioritarias para cada tipo de sistema, y por qué.

| Tipo de sistema | Cualidades prioritarias | ¿Por qué? |
| :--- | :--- | :--- |
| **Sistema de control de una planta industrial** | **Fiabilidad, Robustez y Seguridad (Safety/Security)** | Un fallo no controlado o un comportamiento imprevisto puede poner en riesgo vidas humanas, provocar desastres ambientales o causar pérdidas de infraestructura millonarias. |
| **Red social de uso masivo** | **Escalabilidad, Disponibilidad y Usabilidad** | Debe dar soporte simultáneo a millones de usuarios conectados, mantener tiempos de carga atractivos para retener al usuario e interfaz intuitiva para todo tipo de público. |
| **Sistema de trading financiero de alta frecuencia** | **Eficiencia (Ultra baja latencia) y Corrección** | Las operaciones de compra/venta se realizan en microsegundos. Una demora de milisegundos o un cálculo matemático erróneo genera pérdidas de millones de dólares. |

---

### 11. En tu opinión, ¿es válido que un sistema de consumo masivo tolere una tasa de fallos mayor que un sistema crítico, a cambio de salir antes al mercado? Justifica tu postura.

**Sí, es válido.** En el desarrollo de software de consumo masivo (aplicaciones de entretenimiento, redes sociales, e-commerce), el concepto de *Time-to-Market* es decisivo para capturar usuarios antes que la competencia. Estos sistemas aplican metodologías ágiles donde se lanza un Producto Mínimo Viable (MVP) tolerando fallas menores que no pongan en riesgo la seguridad de los datos de los usuarios. 

Por el contrario, en sistemas críticos (médicos, industriales, aeroespaciales), una falla puede costar vidas o desastres financieros irreversibles, por lo que la tolerancia al fallo debe ser sumamente rigurosa y no se pueden acelerar los tiempos a costa de la fiabilidad.

---

## TEMA 6 · MEDICIÓN DE LA CALIDAD DEL SOFTWARE

### 12. Explica con tus propias palabras por qué se dice que una métrica es “un indicador indirecto de la cualidad, y no la cualidad en sí misma”.

Una cualidad de software (como la mantenibilidad o la usabilidad) es un concepto abstracto y complejo que no se puede medir directamente con una regla o balanza. La métrica proporciona un número cuantitativo sobre un aspecto concreto (por ejemplo, la cantidad de líneas de código o la cobertura de pruebas), lo cual nos da pistas o indicios de cómo está la cualidad, pero no refleja la totalidad del atributo de calidad en su conjunto.

---

### 13. Menciona un riesgo concreto de que un equipo se enfoque en mejorar una métrica de calidad sin revisar si la cualidad real mejoró.

* **Riesgo (Efecto "Lawa de Goodhart"):** Cuando una métrica se convierte en un objetivo, deja de ser una buena métrica.
* **Ejemplo concreto:** Si la gerencia exige al equipo alcanzar un 100% de **cobertura de pruebas unitarias (Code Coverage)** como métrica de fiabilidad, los desarrolladores pueden dedicarse a escribir test vacíos o superficiales que ejecutan las líneas de código sin verificar aserciones reales. La métrica marcará 100%, pero la fiabilidad del software seguirá siendo deficiente porque los tests no detectan fallos lógicos.

---

### 14. Reflexión final: de todo lo visto en la Unidad 2, ¿qué idea te resultó más relevante y por qué?

La idea más relevante es el principio de **"Trade-off" entre cualidades y el impacto del dominio de aplicación**. No existe el "software perfecto en todo": buscar la máxima eficiencia puede destruir la mantenibilidad, y exigir máxima seguridad puede comprometer la usabilidad. Comprender que la calidad del software no es absoluta, sino que depende directamente del contexto de uso y de las prioridades del negocio, es fundamental para tomar decisiones acertadas de diseño y arquitectura en la práctica profesional.