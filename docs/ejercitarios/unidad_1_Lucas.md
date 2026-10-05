# Respuestas — Ejercitario Unidad 01

---

## Tema 1 · Ingeniería de software: una visión previa

**1. En tus propias palabras, define qué es la Ingeniería de Software.**

_Respuesta:_  
La Ingeniería de Software es la aplicación sistemática, disciplinada y cuantificable de principios científicos y de ingeniería al desarrollo, operación y mantenimiento del software. Su objetivo principal es producir software de alta calidad, confiable, dentro del presupuesto y en los plazos previstos.

**2. Explica con un ejemplo la diferencia entre "programar" y "hacer ingeniería de software".**

_Respuesta:_  
- **Programar:** Consiste en escribir código para resolver un problema puntual o crear un script específico (por ejemplo, un estudiante escribiendo un script en Python para procesar un archivo local de texto).  
- **Hacer ingeniería de software:** Implica todo el proceso estructurado alrededor de la solución: analizar los requerimientos del usuario, diseñar la arquitectura del sistema, gestionar la base de datos, implementar pruebas automatizadas, coordinar la integración en equipo y planificar el mantenimiento a largo plazo (por ejemplo, construir un sistema web bancario que soporte miles de transacciones concurrentes con seguridad y alta disponibilidad).

**3. Menciona dos razones por las cuales la ingeniería de software es necesaria en el desarrollo de sistemas actuales.**

_Respuesta:_  
1. **Complejidad y escala de los sistemas:** Los sistemas modernos gestionan volúmenes masivos de datos y concurrencia, lo que exige arquitecturas estructuradas para evitar que el software se vuelva inmanejable.  
2. **Control de costos, tiempos y calidad:** Sin procesos y metodologías claras, los proyectos tienden a sufrir desviaciones graves en el presupuesto, retrasos en entregas o fallas críticas en producción.

---

## Tema 2 · El rol de la IS en el diseño de sistemas (+ impacto de la IA)

**4. Enumera los elementos que conforman un sistema basado en computadora, además del software.**

_Respuesta:_  
- Hardware (servidores, computadoras, dispositivos).  
- Personas / Usuarios (operadores, administradores, usuarios finales).  
- Datos / Información (bases de datos, archivos de entrada/salida).  
- Procedimientos / Políticas (reglas de negocio, manuales de uso, procesos).  
- Redes y Telecomunicaciones (infraestructura de conectividad).

**5. Describe brevemente la diferencia entre una visión sistémica y una visión aislada del software en el diseño de sistemas.**

_Respuesta:_  
- **Visión aislada:** Trata al software como un componente independiente, enfocándose únicamente en el código sin considerar el entorno donde operará.  
- **Visión sistémica:** Entiende al software como parte de un todo interconectado, evaluando cómo interactúa con el hardware, los usuarios, las redes y los procesos organizacionales para asegurar la coherencia del sistema global.

**6. Elige una herramienta de inteligencia artificial aplicada al desarrollo de software (por ejemplo, un asistente de código o de testing) e indica:**
- Qué tarea del ingeniero de software apoya o transforma.
- Un beneficio concreto que ofrece.
- Un riesgo o desafío que introduce su uso.

_Respuesta:_  
- **Herramienta:** Asistente de código con Inteligencia Artificial (por ejemplo, *GitHub Copilot*).  
- **Tarea que apoya o transforma:** Autocompletado de código, generación de boilerplate, refactorización y redacción inicial de pruebas unitarias.  
- **Beneficio concreto:** Incrementa la velocidad de desarrollo al reducir tareas repetitivas y permitir enfocarse en la lógica de negocio compleja.  
- **Riesgo o desafío:** Puede introducir vulnerabilidades de seguridad o bugs sutiles si el desarrollador acepta las sugerencias sin realizar una revisión crítica (over-reliance o alucinación de código).

---

## Tema 3 · Historia de la ingeniería de software

**7. En tu opinión, ¿por qué la "crisis del software" de 1968 marcó un punto de inflexión para la disciplina?**

_Respuesta:_  
Marcó un punto de inflexión porque evidenció que las técnicas de programación informal de la época eran insuficientes para la creciente complejidad del hardware. La conferencia de la OTAN en 1968 formalizó la necesidad de tratar la creación de software con el mismo rigor, estándares y metodologías aplicadas en las ingenierías tradicionales.

**Ejercicio de relación** (completá con la letra que corresponda a cada número):

| Evento / Período | Descripción |
|---|---|
| A. Programación artesanal (1950s–60s) | **3** |
| B. Crisis del software (1968) | **1** |
| C. Modelo en cascada (1970s–80s) | **5** |
| D. Métodos iterativos (1990s) | **4** |
| E. Metodologías ágiles (2001–hoy) | **2** |

1. Se acuña el término "ingeniería de software" en una conferencia de la OTAN ante fallas y sobrecostos de proyectos.
2. Surge el Manifiesto Ágil; se popularizan Scrum, Kanban y XP.
3. El software se escribía de forma individual, sin procesos formales.
4. Ganan terreno la iteración, el prototipado y los modelos incrementales.
5. Se establecen los primeros procesos formales y estructurados de desarrollo.

---

## Tema 4 · El rol del ingeniero de software

**8. Menciona tres competencias que debe tener un ingeniero de software, además del conocimiento técnico.**

_Respuesta:_  
1. **Comunicación efectiva:** Capacidad para transmitir ideas técnicas a equipos interdisciplinarios y clientes no técnicos.  
2. **Pensamiento crítico y resolución de problemas:** Habilidad para analizar situaciones complejas y proponer la solución más óptima.  
3. **Trabajo en equipo y colaboración:** Disposición para trabajar bajo metodologías colaborativas, realizar revisiones de código y adaptarse a la dinámica grupal.

**9. Describe brevemente qué hace cada uno de los siguientes roles dentro de un equipo de desarrollo:**

| Rol | Descripción |
|---|---|
| **Analista** | Releva, documenta y especifica los requerimientos del sistema traduciendo las necesidades del cliente en reglas de negocio claras para el equipo técnico. |
| **Arquitecto** | Define la estructura de alto nivel del sistema, seleccionando las tecnologías, patrones de diseño y estándares para asegurar escalabilidad, seguridad y desempeño. |
| **Desarrollador** | Escribe, refactoriza y mantiene el código fuente del software implementando las funcionalidades acordadas según los diseños establecidos. |
| **Tester / QA** | Diseña y ejecuta planes de pruebas para verificar que el software cumpla con los requerimientos exigidos y carezca de errores antes de su lanzamiento. |

**10. Caso breve:** Un ingeniero de software descubre, cerca de la fecha de entrega, una falla de seguridad que podría exponer datos de usuarios, pero corregirla retrasaría el proyecto una semana. ¿Qué debería hacer y por qué, considerando la ética profesional?

_Respuesta:_  
Debe **notificar de inmediato a los responsables del proyecto y stakeholders sobre el riesgo crítico**, respaldando la necesidad de posponer el lanzamiento o aplicar un plan de mitigación urgente antes de salir a producción. La ética profesional (reflejada en códigos como el de ACM/IEEE) prioriza la seguridad, privacidad y protección de los usuarios por encima de los compromisos comerciales o de cronograma.

---

## Tema 5 · El ciclo del software

**11. Ordena y nombra las cinco fases genéricas del ciclo de vida del software vistas en clase.**

_Respuesta:_  
1. **Análisis de Requerimientos:** Definición de qué debe hacer el software.  
2. **Diseño:** Especificación de la arquitectura, componentes y estructura de datos.  
3. **Implementación (o Codificación):** Traducción del diseño a código fuente.  
4. **Pruebas (Testing):** Verificación y validación del correcto funcionamiento.  
5. **Mantenimiento y Evolución:** Corrección de errores y adaptación a nuevos cambios tras el despliegue.

**12. ¿Por qué se afirma que el mantenimiento suele ser la fase más costosa del ciclo de vida del software? Da un ejemplo hipotético.**

_Respuesta:_  
El mantenimiento suele representar entre el 60% y 80% del costo total del ciclo de vida porque se extiende durante años después del lanzamiento. Incluye la corrección de errores no detectados, adaptación a nuevos entornos operativos (SO, hardware) y la incorporación de evoluciones continuas solicitadas por el negocio.

- *Ejemplo hipotético:* Un sistema de facturación electrónica lanzado al mercado requiere ajustes permanentes cada vez que la entidad tributaria del país cambia las regulaciones fiscales o añade nuevos requisitos de firma digital, obligando a reestructurar módulos existentes a lo largo del tiempo.

---

## Tema 6 · Relación con otras áreas de la ciencia de la computación

**Completen el siguiente cuadro indicando cómo cada área apoya a la ingeniería de software.**

| Área | ¿Cómo apoya a la Ingeniería de Software? |
|---|---|
| **Estructuras de datos y algoritmos** | Permite optimizar el rendimiento del software, eligiendo la mejor forma de organizar y procesar información con la menor complejidad de tiempo y memoria. |
| **Bases de datos** | Aporta los fundamentos para el modelado, almacenamiento, consulta e integridad de la información persistente que manejan las aplicaciones. |
| **Sistemas operativos** | Proporciona el conocimiento sobre gestión de procesos, concurrencia, memoria y manejo de archivos necesarios para construir software eficiente y compatible con el entorno de ejecución. |
| **Redes** | Permite diseñar e implementar aplicaciones distribuidas, web o cliente-servidor considerando latencias, seguridad, protocolos de comunicación y ancho de banda. |

---

## Tema 7 · Relación con otras disciplinas

**13. Elige dos de las siguientes disciplinas — Administración, Psicología, Economía, Derecho, Comunicación — y explica con un ejemplo concreto cómo se relacionan con el trabajo diario de un ingeniero de software.**

_Respuesta:_  
- **Administración:** Aporta principios de gestión de proyectos, estimación de costos, presupuestos y asignación de recursos.  
  *Ejemplo:* Al planificar un *sprint* en Scrum, el ingeniero debe aplicar nociones de administración para estimar el esfuerzo temporal y cumplir con los hitos comprometidos.
- **Derecho:** Establece el marco legal en materia de licencias de software, propiedad intelectual, contratos de servicios y regulaciones de protección de datos personales.  
  *Ejemplo:* Al integrar una biblioteca de código abierto en un producto comercial, el ingeniero debe revisar la licencia (MIT, GPL, Apache) para garantizar el cumplimiento normativo.

**14. Reflexión final:** de todo lo visto en clase (definición, historia, rol del ingeniero, ciclo del software, relación con otras áreas y disciplinas, e impacto de la IA), ¿qué idea te resultó más relevante y por qué?

_Respuesta:_  
La idea más relevante es entender que la Ingeniería de Software va mucho más allá de escribir código funcional; se trata de una disciplina socio-técnica integral. Comprender el contexto histórico (como la crisis del software) y la importancia del ciclo de vida completo permite ver que la sostenibilidad a largo plazo, la responsabilidad ética sobre la seguridad de los datos y el trabajo colaborativo son tan determinantes para el éxito de un sistema como el rigor técnico en algoritmos y arquitecturas.