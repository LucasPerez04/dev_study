GUÍA DE TRABAJO N.º 3
Principios de la ingeniería de software
Para completar después de la explicación de los temas en clase
|
| Información del Documento | Detalle |
| Asignatura | Ingeniería de Software |
| Unidad | 3 — Principios de la ingeniería de software |
Objetivo de la guía
Consolidar, mediante ejercicios prácticos, los siete principios de la ingeniería de software abordados en la exposición: rigor y formalidad, separación de intereses, modularidad, abstracción, anticipación al cambio, generalidad e incrementalidad.
Instrucciones generales
Responde cada sección utilizando tus propias palabras; evita copiar literalmente del material de clase.
Todas las preguntas abiertas deben responderse con un mínimo de 3 a 5 líneas, salvo que se indique lo contrario.
Las actividades de relación y cuadros deben completarse en su totalidad.
TEMA 1 · RIGOR Y FORMALIDAD
Explica con tus propias palabras la diferencia entre "rigor" y "formalidad" en el desarrollo de software. Da un ejemplo de cada uno.
> El rigor se refiere a un enfoque disciplinado, metódico y cuidadoso para realizar las actividades del software sin apoyarse necesariamente en modelos matemáticos rigurosos (por ejemplo, realizar una revisión por pares siguiendo una lista de verificación). La formalidad, en cambio, es un nivel más estricto de rigor que utiliza bases matemáticas, notaciones lógicas y especificaciones formales para certificar propiedades del software (por ejemplo, demostrar la corrección de un algoritmo mediante métodos matemáticos).
¿Por qué no conviene formalizar por completo todos los aspectos de un proyecto de software? Menciona un caso donde sí valga la pena hacerlo.
> No conviene formalizar todo el proyecto debido a que exige un costo temporal, económico y de complejidad altísimo, disminuyendo la agilidad del desarrollo y haciéndolo inviable para la mayoría de sistemas comerciales. Sin embargo, vale la pena aplicar formalidad completa en sistemas de misión crítica o de alta seguridad, como el software de control de vuelo de un avión o el código de un marcapasos, donde un error puede provocar pérdidas humanas.
TEMA 2 · SEPARACIÓN DE INTERESES
En tus propias palabras, ¿qué significa "separar intereses" en el diseño de un sistema? Da un ejemplo distinto al visto en clase.
> Significa descomponer un problema complejo en partes o aspectos individuales más pequeños y manejables, enfocándose en un solo aspecto a la vez para evitar que las responsabilidades se mezclen. Un ejemplo es la arquitectura de un automóvil, donde el sistema de frenado, la gestión del motor y el sistema de entretenimiento están completamente divididos, permitiendo reparar la radio sin alterar el funcionamiento de los frenos.
Para una aplicación de reservas de vuelos, identifica al menos tres “intereses” o aspectos distintos que deberían mantenerse separados, y explica brevemente por qué.
Procesamiento de pagos: Debe estar aislado por motivos de cumplimiento normativo (PCI-DSS) y seguridad, evitando que un fallo en la interfaz afecte la transacción financiera.
Búsqueda y disponibilidad de vuelos: Se enfoca en realizar consultas eficientes e intensivas a la base de datos sin acoplarse con los detalles del pago o la generación del boleto.
Notificaciones e impresión de boletos: Encargado únicamente de enviar correos electrónicos y generar comprobantes PDF, garantizando que si el servicio de correo falla, no interfiera con la reserva.
TEMA 3 · MODULARIDAD
Explica con tus propias palabras la relación entre modularidad, acoplamiento y cohesión.
> La modularidad es la técnica de dividir un sistema en módulos independientes para facilitar su comprensión y mantenimiento. La meta de una buena modularidad es alcanzar una alta cohesión (que todos los elementos internos de un módulo trabajen enfocados en una única tarea) y un bajo acoplamiento (que la dependencia entre módulos sea mínima), lo que permite cambiar o reemplazar un módulo sin afectar negativamente a los demás.
Completa el siguiente cuadro indicando si cada situación es un ejemplo de "alto acoplamiento" o de "baja cohesión", y justifica tu respuesta.
| Situación | ¿Acoplamiento o cohesión? | Justificación |
| Un módulo de “utilidades” que mezcla validaciones, envío de emails y cálculos financieros | Baja cohesión | Agrupa responsabilidades completamente disímiles e inconexas dentro de una misma clase o unidad de código. |
| Dos módulos que se llaman constantemente entre sí y comparten variables globales | Alto acoplamiento | Tienen una interdependencia excesiva; cualquier cambio en la estructura interna de uno romperá el funcionamiento del otro. |
| Un módulo de “reportes” que además valida los permisos del usuario | Baja cohesión | Mezcla la responsabilidad de generación de informes con la gestión de seguridad y autorización del sistema. |
| Un módulo de autenticación que solo se encarga de validar credenciales | Alta cohesión | Ejemplo de referencia positiva: Todas sus funciones internas están concentradas únicamente en el objetivo específico de autenticar al usuario. |
¿Por qué una interfaz bien definida entre módulos reduce el impacto de los cambios internos de cada uno?
> Porque actúa como un contrato rígido de comunicación que especifica los datos de entrada y salida, ocultando los detalles de la implementación interna. De esta forma, mientras el módulo mantenga intacta la firma de su interfaz, los desarrolladores pueden optimizar, reescribir o corregir el código interno sin alterar ni romper el funcionamiento del resto del sistema.
TEMA 4 · ABSTRACCIÓN
Relación de niveles de abstracción:
| Nivel | Relación | Descripción |
| A. Negocio / Requisitos | 2 | Qué problema resuelve el sistema para el usuario, sin detalles técnicos. |
| B. Diseño / Arquitectura | 3 | Cómo se organizan los componentes del sistema y cómo interactúan entre sí. |
| C. Implementación / Código | 1 | Instrucciones concretas, escritas en un lenguaje de programación. |
(Relación completada en la tabla anterior)
Da un ejemplo de una situación cotidiana (no necesariamente de software) donde se apliquen distintos niveles de abstracción.
> El uso de un automóvil ilustra perfectamente los tres niveles: a nivel de negocio/usuario, la abstracción es la acción de conducir (girar el volante y acelerar para ir de un punto A a un punto B); a nivel de diseño/arquitectura, es comprender cómo la transmisión se conecta con el motor y los frenos; y a nivel de implementación, es el funcionamiento mecánico real de las pistolas, válvulas y la combustión de la gasolina dentro del motor.
TEMA 5 · ANTICIPACIÓN AL CAMBIO
¿Qué significa “anticipar el cambio” en el diseño de software? ¿Implica predecir exactamente qué va a cambiar en el futuro?
> Anticipar el cambio significa diseñar el software con una estructura flexible y adaptable que permita absorber modificaciones futuras con el menor esfuerzo y costo posible. No implica adivinar el futuro con precisión, sino identificar las áreas inherentemente volátiles (como normativas legales, proveedores de API o interfaces) y aislarlas mediante capas de abstracción para que los cambios no afecten todo el sistema.
Para un sistema de pagos en línea, identifica una parte que probablemente cambie en el futuro y propone cómo aislarla del resto del sistema.
> La pasarela de pago (por ejemplo, Stripe o PayPal) es la parte con más probabilidades de cambiar o expandirse. Para aislarla, se debe diseñar una interfaz o patrón adaptador (ej. `ProcesadorPagos`), haciendo que el núcleo del sistema interactúe únicamente con esta interfaz abstracta; si en el futuro se cambia de proveedor de pagos, solo se implementa un nuevo adaptador sin modificar la lógica principal de ventas.
TEMA 6 · GENERALIDAD
¿Cuál es el riesgo de generalizar demasiado una solución? Da un ejemplo concreto de una solución “sobre-generalizada”.
> El riesgo de generalizar en exceso es la sobreingeniería, lo que introduce una complejidad innecesaria, aumenta los costos de desarrollo y dificulta la lectura y mantenimiento del código. Un ejemplo es crear un motor de procesamiento de formularios hiper-genérico capaz de construir cualquier interfaz dinámica para un sistema simple que solo necesitaba un formulario de contacto estático de tres campos.
TEMA 7 · INCREMENTALIDAD
Explica la diferencia entre construir un sistema de forma incremental y construirlo todo de una vez ("big bang").
> La construcción incremental entrega el sistema en fases o módulos funcionales sucesivos, permitiendo obtener retroalimentación temprana del usuario y mitigar riesgos progresivamente. En contraste, el enfoque "big bang" busca construir la totalidad del sistema antes de entregarlo o probarlo con usuarios, lo que aumenta drásticamente el riesgo de retrasos, incompatibilidades y fallas masivas durante el lanzamiento final.
Reflexión final: de los siete principios vistos en la Unidad 3, ¿cuál te parece más difícil de aplicar en la práctica, y por qué?
> La **anticipación al cambio** suele ser la más difícil de aplicar en la práctica porque exige un equilibrio delicado entre el diseño intuitivo y la sobreingeniería. Es un reto constante decidir dónde agregar abstracciones para el futuro sin caer en la tentación de programar características no requeridas que encarecen el proyecto hoy (violando el principio de simplicidad).
— Fin de la guía de trabajo —