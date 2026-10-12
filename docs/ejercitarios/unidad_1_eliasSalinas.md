GUÍA DE TRABAJO N.º 1
Ingeniería de Software: una visión previa
Para completar después de la explicación de los temas en clase
Información del Documento	Detalle
Asignatura	Ingeniería de Software
Unidad	1 — Fundamentos
Modalidad	Individual
Duración sugerida	45–60 minutos
Nombre del estudiante	Elias Salinas
Objetivo de la guía
Consolidar, mediante ejercicios prácticos, los conceptos abordados en la exposición sobre los fundamentos de la Ingeniería de Software: su definición, su rol en el diseño de sistemas, su historia, el rol del ingeniero de software, el ciclo del software y su relación con otras áreas y disciplinas.
Instrucciones generales
Responde cada sección utilizando tus propias palabras; evita copiar literalmente del material de clase.
Todas las preguntas abiertas deben responderse con un mínimo de 3 a 5 líneas, salvo que se indique lo contrario.
Las actividades de relación y cuadros deben completarse en su totalidad.
---
TEMA 1 · INGENIERÍA DE SOFTWARE: UNA VISIÓN PREVIA
En tus propias palabras, define qué es la Ingeniería de Software.
> La Ingeniería de Software es una disciplina de la ingeniería que aplica principios, métodos, procesos y herramientas sistemáticas y cuantificables al desarrollo, operación y mantenimiento del software. Su objetivo principal es producir programas confiables, eficientes, mantenibles y seguros que satisfagan las necesidades del usuario dentro de los límites de presupuesto y tiempo establecidos.
Explica con un ejemplo la diferencia entre "programar" y "hacer ingeniería de software".
> Programar consiste en escribir código fuente en un lenguaje de programación para resolver un problema específico o implementar un algoritmo puntual (por ejemplo, un estudiante escribiendo una función para ordenar una lista). En cambio, hacer ingeniería de software abarca todo un proceso integral que incluye el análisis de requisitos, arquitectura, diseño de interfaces, pruebas automatizadas, gestión del proyecto y mantenimiento continuo para crear una solución robusta y escalable (por ejemplo, diseñar la plataforma completa de banca en línea de un banco nacional).
Menciona dos razones por las cuales la ingeniería de software es necesaria en el desarrollo de sistemas actuales.
Complejidad y escala de los sistemas actuales: Los programas modernos gestionan millones de usuarios e interacciones simultáneas, exigiendo arquitecturas organizadas para evitar fallas masivas.
Control de costos y tiempos: Proporciona metodologías y estándares que reducen la probabilidad de sobrecostos, retrasos o la entrega de productos defectuosos.
---
TEMA 2 · EL ROL DE LA IS EN EL DISEÑO DE SISTEMAS (+ IMPACTO DE LA IA)
Enumera los elementos que conforman un sistema basado en computadora, además del software.
Hardware: Equipos físicos, procesadores, memoria y periféricos.
Personas / Usuarios: Operadores, administradores y usuarios finales.
Datos e Información: Bases de datos, archivos de configuración y estructuras de información.
Procedimientos / Documentación: Reglas de negocio, procesos organizacionales y manuales de usuario.
Redes y Comunicaciones: Infraestructura de red, protocolos e interfaces de comunicación.
Describe brevemente la diferencia entre una visión sistémica y una visión aislada del software en el diseño de sistemas.
> La visión aislada se enfoca únicamente en la lógica interna del programa y en escribir código sin considerar el entorno donde se desplegará. Por otro lado, la visión sistémica contempla el software como una parte interconectada de un todo mayor, analizando cómo interactúa con el hardware, los procesos organizacionales, las restricciones de red y los usuarios finales para garantizar un funcionamiento armónico y global.
Elige una herramienta de inteligencia artificial aplicada al desarrollo de software (por ejemplo, un asistente de código o de testing) e indica:
Herramienta: GitHub Copilot.
Tarea que apoya o transforma: Apoya y acelera la escritura de código, autocompletado de funciones, generación de pruebas unitarias y documentación de funciones en tiempo real.
Beneficio concreto: Incrementa significativamente la productividad al reducir el tiempo dedicado a escribir código repetitivo o buscar sintaxis básica en documentación externa.
Riesgo o desafío: Puede generar código con vulnerabilidades de seguridad, errores de lógica sutiles o sesgos, lo que exige una revisión humana minuciosa y crítica.
---
TEMA 3 · HISTORIA DE LA INGENIERÍA DE SOFTWARE
Relación de eventos históricos:
Evento / Período	Relación	Descripción
A. Programación artesanal (1950s–60s)	3	El software se escribía de forma individual, sin procesos formales.
B. Crisis del software (1968)	1	Se acuña el término "ingeniería de software" en una conferencia de la OTAN ante fallas y sobrecostos de proyectos.
C. Modelo en cascada (1970s–80s)	5	Se establecen los primeros procesos formales y estructurados de desarrollo.
D. Métodos iterativos (1990s)	4	Ganan terreno la iteración, el prototipado y los modelos incrementales.
E. Metodologías ágiles (2001–hoy)	2	Surge el Manifiesto Ágil; se popularizan Scrum, Kanban y XP.
En tu opinión, ¿por qué la "crisis del software" de 1968 marcó un punto de inflexión para la disciplina?
> Marcó un punto de inflexión porque evidenció públicamente que la programación empírica e informal no era suficiente para construir sistemas informáticos complejos e industriales. Al admitir que los proyectos superaban sistemáticamente sus presupuestos, no cumplían los plazos y entregaban software inestable, la comunidad científica reconoció la necesidad urgente de aplicar el rigor técnico, la planificación y los estándares propios de la ingeniería tradicional.
---
TEMA 4 · EL ROL DEL INGENIERO DE SOFTWARE
Menciona tres competencias que debe tener un ingeniero de software, además del conocimiento técnico.
Pensamiento crítico y resolución de problemas complejos.
Comunicación efectiva y trabajo colaborativo en equipo.
Adaptabilidad y capacidad de aprendizaje continuo e autónomo.
Describe brevemente qué hace cada uno de los siguientes roles dentro de un equipo de desarrollo:
Rol	Descripción de funciones
Analista	Levanta, especifica y documenta los requisitos y necesidades del usuario y del negocio para traducirlos en especificaciones técnicas del software.
Arquitecto	Define la estructura de alto nivel del sistema, seleccionando las tecnologías, patrones de diseño y estándares técnicos adecuados para garantizar escalabilidad y rendimiento.
Desarrollador	Escribe, implementa y mantiene el código fuente del sistema siguiendo los diseños y especificaciones arquitectónicas establecidas.
Tester / QA	Diseña y ejecuta planificaciones de pruebas para identificar errores, verificar el cumplimiento de requisitos y asegurar la calidad global del producto antes de su liberación.
Caso breve: Un ingeniero de software descubre, cerca de la fecha de entrega, una falla de seguridad que podría exponer datos de usuarios, pero corregirla retrasaría el proyecto una semana. ¿Qué debería hacer y por qué, considerando la ética profesional?
> El ingeniero de software debe reportar de inmediato la falla crítica a los responsables del proyecto y stakeholders, recomendando posponer el lanzamiento hasta solucionar el problema. Desde la perspectiva de la ética profesional, la protección de la privacidad y los datos de los usuarios es prioritaria sobre los compromisos comerciales o de tiempo; lanzar un software a sabiendas de un riesgo de seguridad vulnera la confianza y el código deontológico de la profesión.
---
TEMA 5 · EL CICLO DEL SOFTWARE
Ordena y nombra las cinco fases genéricas del ciclo de vida del software vistas en clase.
Comunicación / Análisis de Requisitos
Planeación / Diseño del Sistema
Construcción / Codificación
Despliegue / Pruebas e Instalación
Mantenimiento y Evolución
¿Por qué se afirma que el mantenimiento suele ser la fase más costosa del ciclo de vida del software? Da un ejemplo hipotético.
> Se afirma esto porque la fase de mantenimiento abarca la mayor parte de la vida útil del sistema (años o décadas), durante la cual se deben adaptar las funciones a nuevos entornos tecnológicos, corregir errores no detectados previamente y responder a los cambios en las reglas de negocio. Por ejemplo, una tienda en línea necesita actualizar su sistema constantemente para integrarse con nuevos métodos de pago, cumplir con regulaciones fiscales cambiantes y adaptarse al aumento del tráfico anual.
---
TEMA 6 · RELACIÓN CON OTRAS ÁREAS DE LA CIENCIA DE LA COMPUTACIÓN
Área	¿Cómo apoya a la Ingeniería de Software?
Estructuras de datos y algoritmos	Permite diseñar soluciones computacionales eficientes, optimizando el consumo de memoria y el tiempo de procesamiento en la ejecución del software.
Bases de datos	Proporciona las técnicas e infraestructura necesarias para almacenar, consultar, organizar y gestionar la información de manera persistente, segura y consistente.
Sistemas operativos	Ofrece la interfaz y abstracción con el hardware, permitiendo gestionar adecuadamente hilos, procesos, recursos de memoria y operaciones de entrada/salida.
Redes	Facilita la comunicación entre componentes distribuidos, garantizando la conectividad, intercambio de datos seguro y la arquitectura cliente-servidor o de microservicios.
---
TEMA 7 · RELACIÓN CON OTRAS DISCIPLINAS
Elige dos de las siguientes disciplinas — Administración, Psicología, Economía, Derecho, Comunicación — y explica con un ejemplo concreto cómo se relacionan con el trabajo diario de un ingeniero de software.
Administración: Se relaciona con la gestión de proyectos, estimación de recursos, control de presupuestos y asignación de tiempos. Un ejemplo es cuando un líder técnico aplica metodologías de gestión para estimar las horas de trabajo y coordinar las entregas del equipo.
Derecho: Se relaciona con los aspectos legales del software, como licencias de código abierto, propiedad intelectual, contratos de nivel de servicio (SLA) y normativas de protección de datos. Por ejemplo, el ingeniero debe asegurarse de no violar licencias de bibliotecas de terceros al integrarlas en un producto comercial.
Reflexión final: de todo lo visto en clase (definición, historia, rol del ingeniero, ciclo del software, relación con otras áreas y disciplinas, e impacto de la IA), ¿qué idea te resultó más relevante y por qué?
> La idea más relevante es entender que la Ingeniería de Software va mucho más allá de simplemente escribir código, abarcando una visión integral de resolución de problemas de forma profesional, metódica e interdisciplinaria. Además, el impacto actual de la Inteligencia Artificial resalta que las habilidades clave de un ingeniero del futuro no serán la memorización de sintaxis, sino el criterio arquitectónico, la capacidad analítica, el juicio ético y la comunicación efectiva.
---
— Fin de la guía de trabajo —