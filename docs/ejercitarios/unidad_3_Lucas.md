# Respuestas — Ejercitario Unidad 03 Test

---

## Tema 1 · Rigor y formalidad

**1. Explica con tus propias palabras la diferencia entre "rigor" y "formalidad" en el desarrollo de software. Da un ejemplo de cada uno.**

_Respuesta:_  
- **Rigor:** Es una actitud de precisión, exactitud y disciplina durante todo el proceso de desarrollo, sin necesidad de recurrir a modelos matemáticos estrictos.  
  *Ejemplo:* Seguir de forma estricta un protocolo de revisiones de código (*code reviews*), realizar pruebas de integración continuas y mantener un estándar de codificación riguroso en el equipo.
- **Formalidad:** Es el nivel más elevado de rigor, caracterizado por el uso de notaciones, modelos o demostraciones matemáticas para especificar, diseñar o verificar un sistema.  
  *Ejemplo:* Utilizar especificaciones algebraicas o lógica de Hoare (como métodos formales Z o B) para demostrar matemáticamente que un módulo no producirá condiciones de carrera.

**2. ¿Por qué no conviene formalizar por completo todos los aspectos de un proyecto de software? Menciona un caso donde sí valga la pena hacerlo.**

_Respuesta:_  
No conviene formalizar todo el proyecto debido al altísimo costo económico, de tiempo y a la complejidad de aprendizaje que implica. La formalización completa ralentiza el ritmo de desarrollo y dificulta la flexibilidad ante requerimientos cambiantes en software comercial común.

- *Caso donde sí vale la pena:* En **sistemas críticos de misión o de vida** (como el software de control de un marcapasos, los sistemas de aviónica de un avión comercial o el software de control de una planta nuclear), donde una falla en el sistema representa pérdidas humanas o catastróficas.

---

## Tema 2 · Separación de intereses

**3. En tus propias palabras, ¿qué significa "separar intereses" en el diseño de un sistema? Da un ejemplo distinto al visto en clase.**

_Respuesta:_  
Significa descomponer un problema complejo en partes o aspectos independientes, permitiendo analizar, diseñar y modificar cada aspecto por separado sin tener que entender o afectar todo el sistema al mismo tiempo.

- *Ejemplo:* En un sistema e-commerce, separar el **módulo de notificaciones** (envío de emails/SMS) del **módulo de procesamiento de inventario**. Si mañana se cambia el proveedor de envíos de correo (de SendGrid a Mailgun), el cálculo de stock no se ve afectado en lo absoluto.

**4. Para una aplicación de reservas de vuelos, identifica al menos tres "intereses" o aspectos distintos que deberían mantenerse separados, y explica brevemente por qué.**

_Respuesta:_  
1. **Interfaz de usuario (UI):** La presentación gráfica donde el cliente busca vuelos. Se separa para poder rediseñar la interfaz o crear una app móvil sin tocar la lógica de negocio.  
2. **Lógica de pasarela de pago:** El procesamiento transaccional de cobros con tarjetas. Se aisla por temas de seguridad, cumplimiento de estándares (PCI-DSS) y facilidad para cambiar de proveedor de pago.  
3. **Gestión de disponibilidad y asientos (Inventario):** La lógica de concurrencia para evitar el *overbooking*. Se separa para optimizar el rendimiento y las consultas a la base de datos de manera independiente.

---

## Tema 3 · Modularidad

**5. Explica con tus propias palabras la relación entre modularidad, acoplamiento y cohesión.**

_Respuesta:_  
La **modularidad** es la técnica de dividir un sistema en módulos independientes. Para lograr una modularidad ideal, los módulos deben buscar una **alta cohesión** (que las responsabilidades internas de un módulo estén fuertemente relacionadas entre sí) y un **bajo acoplamiento** (que la dependencia e interconexión entre distintos módulos sea la mínima posible).

**6. Completa el siguiente cuadro indicando si cada situación es un ejemplo de "alto acoplamiento" o de "baja cohesión", y justifica tu respuesta.**

| Situación | ¿Acoplamiento o cohesión? | Justificación |
| --- | --- | --- |
| Un módulo de "utilidades" que mezcla validaciones, envío de emails y cálculos financieros | **Baja cohesión** | Realiza tareas completamente dispares que no tienen relación temática ni de negocio entre sí. |
| Dos módulos que se llaman constantemente entre sí y comparten variables globales | **Alto acoplamiento** | Dependen íntimamente el uno del otro, lo que impide modificar o probar uno sin afectar al otro. |
| Un módulo de "reportes" que además valida los permisos del usuario | **Baja cohesión** | Mezcla la responsabilidad de generar informes con la responsabilidad de seguridad/autorización. |
| Un módulo de autenticación que solo se encarga de validar credenciales | **Alta cohesión / Bajo acoplamiento** | *(Ejemplo de buena práctica)* Sus funciones están enfocadas exclusivamente en la autenticación. |

**7. ¿Por qué una interfaz bien definida entre módulos reduce el impacto de los cambios internos de cada uno?**

_Respuesta:_  
Porque actúa como un **contrato**. La interfaz especifica *qué* hace el módulo (entradas y salidas) sin revelar *cómo* lo hace internamente (encapsulamiento). Mientras la firma de la interfaz no cambie, la implementación interna del módulo se puede refactorizar o reescribir por completo sin romper los demás módulos que la consumen.

---

## Tema 4 · Abstracción

Relaciona cada nivel de abstracción con su descripción correspondiente (completá con el número que corresponda a cada letra).

**8. Relaciona cada nivel con su descripción:**

| Nivel | N.º de descripción |
| --- | --- |
| A. Negocio / Requisitos | **2** |
| B. Diseño / Arquitectura | **3** |
| C. Implementación / Código | **1** |

1. Instrucciones concretas, escritas en un lenguaje de programación.
2. Qué problema resuelve el sistema para el usuario, sin detalles técnicos.
3. Cómo se organizan los componentes del sistema y cómo interactúan entre sí.

**9. Da un ejemplo de una situación cotidiana (no necesariamente de software) donde se apliquen distintos niveles de abstracción.**

_Respuesta:_  
*Ejemplo: Conducir un automóvil.*
- **Nivel Negocio / Requisitos:** "Quiero ir del punto A al punto B de manera cómoda y segura."  
- **Nivel Diseño / Arquitectura:** El vehículo expone mandos principales: volante, pedal de acelerador, freno y palanca de cambios.  
- **Nivel Implementación / Código:** El funcionamiento interno del motor de combustión o eléctrico, la inyección de combustible y el sistema hidráulico de frenado ABS.

---

## Tema 5 · Anticipación al cambio

**10. ¿Qué significa "anticipar el cambio" en el diseño de software? ¿Implica predecir exactamente qué va a cambiar en el futuro?**

_Respuesta:_  
Significa diseñar el software identificando las áreas propensas a cambios y estructurando el código de modo que esos cambios puedan absorberse con el menor impacto posible. **No implica adivinar el futuro**, sino aplicar principios (como encapsulamiento e interfaces) para que los componentes sean flexibles frente a eventuales modificaciones.

**11. Para un sistema de pagos en línea, identifica una parte que probablemente cambie en el futuro y propone cómo aislarla del resto del sistema.**

_Respuesta:_  
- **Parte propensa a cambios:** La pasarela de pago externa (p. ej., Stripe, PayPal o bancos locales).  
- **Propuesta para aislarla:** Utilizar el patrón de diseño *Adapter* o una interfaz común (p. ej., `IPaymentGateway` con métodos `processPayment()` y `refund()`). De esta forma, la lógica del sistema interactúa solo con la interfaz, y si se añade o cambia de proveedor de pago, solo se crea una nueva implementación sin modificar el código del checkout.

---

## Tema 6 · Generalidad

**12. ¿Cuál es el riesgo de generalizar demasiado una solución? Da un ejemplo concreto de una solución "sobre-generalizada".**

_Respuesta:_  
El riesgo de la sobre-generalización es la **complejidad innecesaria** (Over-engineering), lo que deriva en código difícil de leer, mantener, probar y en una pérdida de rendimiento.

- *Ejemplo concreto:* Crear un motor genérico de formularios con soporte para reglas dinámicas complejas escritas en un DSL propio, cuando el cliente solo necesitaba un formulario de contacto estático de 3 campos.

---

## Tema 7 · Incrementalidad

**13. Explica la diferencia entre construir un sistema de forma incremental y construirlo todo de una vez ("big bang").**

_Respuesta:_  
- **Incremental:** El sistema se entrega por partes funcionales en iteraciones sucesivas. Cada incremento agrega valor utilizable por el usuario, permitiendo obtener retroalimentación temprana y mitigar riesgos progresivamente.  
- **Big Bang:** Todo el sistema se diseña, desarrolla y prueba completo en una única fase prolongada antes de entregarlo al cliente. Si surgen errores de comprensión o fallas de arquitectura, se descubren al final, cuando corregirlos es sumamente costoso.

**14. Reflexión final: de los siete principios vistos en la Unidad 3, ¿cuál te parece más difícil de aplicar en la práctica, y por qué?**

_Respuesta:_  
El principio de **Generalidad** (o el equilibrio entre Generalidad y Anticipación al Cambio). Es especialmente complejo definir el límite justo entre hacer un código lo suficientemente flexible para futuras adaptaciones sin caer en la sobre-ingeniería (*Over-engineering*). Decidir cuándo mantener las cosas simples (principio YAGNI: "You Aren't Gonna Need It") frente a cuándo abstraer para el futuro requiere mucha experiencia y criterio.