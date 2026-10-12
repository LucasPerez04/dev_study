```markdown
# Unidad 4 — Diseño del Software

## Ejercitario Resuelto

| Campo | Detalle |
|---|---|
| **Materia** | Ingeniería de Software 1 |
| **Unidad** | 4 — Diseño del software |
| **Temas cubiertos** | Actividad del diseño y sus objetivos · Técnicas de modularización · Notaciones de diseño · Paradigma orientado a objetos · Diseño de la interfaz de usuario 

---

## Tema 1 — Actividad del diseño del software y sus objetivos

**1.** Explique con sus propias palabras la diferencia entre diseño arquitectónico y diseño detallado. Dé un ejemplo de cada uno para un sistema de reservas de vuelos.

> **Respuesta:**
> El **diseño arquitectónico** define la estructura global del sistema a alto nivel[cite: 3], identificando sus grandes componentes, subsistemas y la forma en que se comunican entre sí. Por otro lado, el **diseño detallado** se enfoca en la estructura interna de cada componente individual, especificando sus algoritmos, estructuras de datos y lógica interna previa a la codificación.
> 
> * **Ejemplo de diseño arquitectónico:** Diseñar un sistema de reservas de vuelos dividiéndolo en tres capas/módulos principales: *Interfaz de Usuario (Web/Mobile)*, *Módulo de Negocio de Reservas y Vuelos*, y *Servicio Externo de Pasarela de Pagos*, conectados mediante una arquitectura cliente-servidor o API REST[cite: 3].
> * **Ejemplo de diseño detallado:** Especificar el algoritmo interno y la estructura de datos para el método `calcularTarifaAsiento(asientoId, pasajeroTipo)` dentro del módulo de reservas, contemplando promociones, disponibilidad y clases de asiento.

---

**2.** *(Verdadero o Falso — justifique su respuesta)*
"El diseño de software tiene una única solución óptima para cada especificación."

> **Respuesta:** **FALSO.**
> 
> **Justificación:** El diseño de software es un proceso de exploración de compromisos (*trade-offs*). Un mismo conjunto de requerimientos o especificaciones admite múltiples soluciones arquitectónicas válidas[cite: 3]. La elección de una u otra depende de qué atributos de calidad se prioricen (como rendimiento, mantenibilidad, tiempo de desarrollo, costo o seguridad), por lo que no existe una solución única ni absoluta.

---

## Tema 2 — Técnicas de modularización

**3.** Defina el criterio de ocultamiento de información de Parnas y explique por qué reduce el impacto de los cambios futuros sobre el sistema.

> **Respuesta:**
> El criterio de ocultamiento de información (*information hiding*) propuesto por David Parnas establece que un módulo debe ocultar sus decisiones de diseño difíciles o propensas a cambiar (tales como algoritmos internos o estructuras de datos específicas) detrás de una interfaz pública clara y estable[cite: 3].
> 
> Esto reduce el impacto de cambios futuros porque, si los detalles de implementación cambian (por ejemplo, migrar de una base de datos relacional a una NoSQL o cambiar una lista por un árbol de búsqueda), únicamente se modifica el código interno de ese módulo. Todos los demás módulos que interactúan con él a través de la interfaz permanecen intactos y sin afectar al resto del sistema.

---

**4.** Compare la descomposición top-down y bottom-up: mencione una ventaja y una desventaja de cada enfoque.

> **Respuesta:**
> 
> * **Descomposición Top-Down (De arriba hacia abajo):**
>   * *Ventaja:* Mantiene el foco en el objetivo general del negocio y la funcionalidad global del sistema desde el inicio, facilitando la validación rápida con las partes interesadas.
>   * *Desventaja:* Los componentes de bajo nivel no se prueban ni implementan hasta fases avanzadas, lo que puede postergar la detección de problemas técnicos o de factibilidad detallada.
> 
> * **Descomposición Bottom-Up (De abajo hacia arriba):**
>   * *Ventaja:* Promueve la reutilización de código y componentes base probados y confiables, garantizando la solidez de las operaciones fundamentales.
>   * *Desventaja:* Corre el riesgo de construir módulos o servicios de nivel inferior que luego no encajen de manera eficiente o coherente con los requerimientos generales del sistema.

---

**5.** *(Aplicación)* Dado un sistema de gestión de biblioteca, proponga una modularización por tipos de datos abstractos, indicando al menos dos módulos junto con su interfaz pública (operaciones que exponen).

> **Respuesta:**
> 
> **Módulo 1: `TDA_Libro`**
> * **Descripción:** Encapsula la información y operaciones relativas al catálogo de libros y su disponibilidad física/digital.
> * **Interfaz pública (operaciones que expone):**
>   * `crearLibro(isbn, titulo, autor, anio) : Libro`
>   * `obtenerEstado(isbn) : EstadoLibro`
>   * `cambiarEstado(isbn, nuevoEstado) : Boolean`
> 
> **Módulo 2: `TDA_Prestamo`**
> * **Descripción:** Gestiona las transacciones de alquiler y devolución de libros a los usuarios de la biblioteca.
> * **Interfaz pública (operaciones que expone):**
>   * `registrarPrestamo(idUsuario, isbn, fechaDevolucion) : Prestamo`
>   * `registrarDevolucion(idPrestamo) : Boolean`
>   * `calcularMulta(idPrestamo) : Flotante`

---

## Tema 3 — Notaciones de diseño

**6.** ¿Qué información transmite un diagrama de estructura (structure chart) que no transmite un diagrama de clases UML, y viceversa?

> **Respuesta:**
> 
> * **Información que transmite el Diagrama de Estructura (*structure chart*) y no el Diagrama de Clases UML:** Transmite la jerarquía de llamadas a procedimientos/funciones de un sistema estructurado, detallando el flujo de control procedimental, las decisiones condicionales, los bucles de ejecución y el paso de parámetros de datos y de control entre módulos[cite: 3].
> * **Información que transmite el Diagrama de Clases UML y no el Diagrama de Estructura:** Transmite la estructura estática orientada a objetos[cite: 3], incluyendo las clases con sus atributos y métodos, los niveles de visibilidad, e interrelaciones como herencia, asociación, agregación, composición e implementación de interfaces.

---

**7.** Escriba en PDL (pseudocódigo) el algoritmo para calcular el promedio de una lista de calificaciones, excluyendo los valores nulos.

> **Respuesta:**
> ```text
> ALGORITMO CalcularPromedioSinNulos(listaCalificaciones)
>     ENTRADA: listaCalificaciones (Lista de Números)
>     SALIDA: promedio (Número)
> 
>     VAR suma <- 0.0
>     VAR contadorValidos <- 0
> 
>     PARA CADA nota EN listaCalificaciones HACER
>         SI nota NO ES NULO ENTONCES
>             suma <- suma + nota
>             contadorValidos <- contadorValidos + 1
>         FIN SI
>     FIN PARA
> 
>     SI contadorValidos > 0 ENTONCES
>         promedio <- suma / contadorValidos
>     SINO
>         promedio <- 0.0
>     FIN SI
> 
>     RETORNAR promedio
> FIN ALGORITMO
> ```

---

**8.** Complete el siguiente enunciado:

> El diagrama UML de **secuencia**[cite: 3] documenta la interacción dinámica entre objetos concretos a lo largo del tiempo, mientras que el diagrama de **clases**[cite: 3] documenta la estructura estática de clases, atributos y relaciones.

---

## Tema 4 — El paradigma orientado a objetos (Análisis y Diseño OO)

**9.** Defina encapsulamiento, herencia y polimorfismo, aportando un ejemplo propio para cada concepto (no utilice los ejemplos vistos en clase).

> **Respuesta:**
> 
> * **Encapsulamiento:** Es el principio que agrupa datos y métodos que operan sobre ellos dentro de una clase, restringiendo el acceso directo al estado interno desde el exterior[cite: 3].
>   * *Ejemplo:* La clase `CuentaBancaria` mantiene la variable `saldo` privada. Para modificar el saldo, el cliente debe usar los métodos `depositar(monto)` o `retirar(monto)`, los cuales validan que los valores sean positivos y que exista fondo suficiente.
> * **Herencia:** Es el mecanismo mediante el cual una subclase adquiere atributos y métodos de una clase superior (superclase), permitiendo extender y reutilizar el comportamiento base[cite: 3].
>   * *Ejemplo:* Una clase base `DispositivoElectronico` posee los atributos `marca` y `modelo`. Las subclases `TelefonoInteligente` y `ComputadoraPortatil` heredan de ella y añaden sus propios métodos específicos, como `hacerLlamada()` o `conectarHDMI()`.
> * **Polimorfismo:** Es la capacidad de responder de manera diferente a una misma llamada o mensaje, dependiendo del tipo de objeto que lo reciba[cite: 3].
>   * *Ejemplo:* La interfaz `Notificador` tiene el método `enviarMensaje()`. Las clases `NotificadorEmail`, `NotificadorSMS` y `NotificadorPush` implementan `enviarMensaje()`, ejecutando cada una la lógica específica según su medio de comunicación.

---

**10.** Explique la diferencia entre Análisis Orientado a Objetos (AOO) y Diseño Orientado a Objetos (DOO). ¿En qué etapa aparecen típicamente las clases de solución, como las de acceso a base de datos?

> **Respuesta:**
> 
> * **AOO (Análisis Orientado a Objetos):** Se centra en comprender y modelar el dominio del problema[cite: 3]. Su objetivo es identificar las clases y conceptos del negocio (clases del dominio) desde la perspectiva del usuario, enfocándose en *qué* debe hacer el sistema.
> * **DOO (Diseño Orientado a Objetos):** Se enfoca en definir las soluciones técnicas para implementar los requerimientos analizados[cite: 3]. Considera aspectos del entorno de software, rendimiento y arquitectura, definiendo *cómo* funcionará el sistema.
> 
> **¿En qué etapa aparecen las clases de solución?**
> Aparecen típicamente en la etapa de **Diseño Orientado a Objetos (DOO)**[cite: 3], ya que corresponden a detalles tecnológicos e infraestructura (como `ConexionBD`, `GestorMantenimiento`, adaptadores de APIs externas o gestores de interfaz de usuario).

---

**11.** *(Aplicación — tarjeta CRC)* Elabore una tarjeta CRC para la clase `Factura` en un sistema de facturación electrónica, indicando al menos tres responsabilidades y dos colaboradores.

> **Respuesta:**
> 
> | **Nombre de la clase:** `Factura` | |
> |---|---|
> | **Responsabilidades** | **Colaboradores** |
> | 1. Calcular el monto total de la venta sumando los ítems y aplicando impuestos. | `ItemFactura` |
> | 2. Generar el código de autorización fiscal (firma electrónica). | `ServicioFirmaDigital` |
> | 3. Validar el estado del pago y asociar la transacción al comprador. | `Cliente` |

---

**12.** A partir de la siguiente especificación textual:

> "El sistema debe permitir que un Cliente realice un Pedido compuesto por uno o más Ítems, y que un Vendedor apruebe dicho Pedido."

Identifique las clases candidatas aplicando la técnica de análisis de sustantivos/verbos, indicando qué sustantivos sugieren clases y qué verbos sugieren operaciones.

> **Respuesta:**
> 
> **Sustantivos (Clases Candidatas):**
> * `Cliente`: Clase que representa al usuario comprador.
> * `Pedido`: Clase que contiene la orden de compra.
> * `Item`: Clase que representa el producto y cantidad solicitados.
> * `Vendedor`: Clase que representa al agente que procesa las órdenes.
> 
> **Verbos (Operaciones / Métodos Candidatos):**
> * *realice*: Operación `realizarPedido()` (asociada a `Cliente` o `Pedido`).
> * *compuesto*: Relación de agregación/composición entre `Pedido` e `Item`.
> * *apruebe*: Operación `aprobarPedido()` (asociada a `Vendedor` o `Pedido`).

---

**13.** Explique el principio de sustitución de Liskov y proponga un contraejemplo: un caso de diseño en el que este principio se viole.

> **Respuesta:**
> El **Principio de Sustitución de Liskov (LSP)** establece que las clases derivadas (subclases) deben poder sustituir a sus clases base (superclases) sin alterar el funcionamiento ni el comportamiento esperado del sistema.
> 
> **Contraejemplo de violación de LSP:**
> * Clase base: `Ave`, con el método `volar()`.
> * Subclase: `Pinguino` hereda de `Ave`.
> 
> **Violación:** Dado que un pingüino es un ave pero no puede volar, la implementación de `volar()` en `Pinguino` tendría que lanzar una excepción (ejemplo: `UnsupportedOperationException`). Si un programa itera sobre una lista de tipo `Ave` e invoca `ave.volar()`, fallará al llegar al objeto `Pinguino`, rompiendo la sustitución transparente y violando el principio LSP.

---

**14.** *(Verdadero o Falso — justifique su respuesta)*
"El polimorfismo permite que distintas subclases implementen de forma diferente un mismo método heredado de la superclase."

> **Respuesta:** **VERDADERO.**
> 
> **Justificación:** Esa es la definición básica del polimorfismo por sobrescritura de métodos (*overriding*)[cite: 3]. Permite que la superclase defina una firma de método genérica, mientras que cada subclase provee su propia implementación según sus necesidades específicas, respondiendo de forma acorde al ser ejecutadas dinámicamente.

---

## Tema 5 — Diseño de la interfaz del usuario

**15.** Mencione tres heurísticas de usabilidad de Nielsen y explique cómo aplicaría cada una al diseño de un formulario de registro de usuarios.

> **Respuesta:**
> 
> 1. **Visibilidad del estado del sistema:**
>    * *Aplicación:* Mostrar una barra de progreso que indique los pasos del registro ("Paso 1 de 3") e indicar visualmente cuando una contraseña cumple los requisitos en tiempo real mediante un indicador dinámico.
> 2. **Prevención de errores:**
>    * *Aplicación:* Deshabilitar el botón "Registrar" hasta que los campos obligatorios estén completados correctamente y utilizar selectores de fecha (*datepickers*) para evitar formatos de fecha inválidos.
> 3. **Reconocimiento antes que recuerdo:**
>    * *Aplicación:* Incluir etiquetas claras visibles sobre los campos, textos de sugerencia (*placeholders*) con ejemplos de llenado y listas desplegables para la selección de datos estándar (como país o ciudad), evitando que el usuario tenga que memorizar la sintaxis.

---

**16.** Explique por qué la separación entre interfaz y lógica de negocio (por ejemplo, mediante el patrón MVC) facilita el mantenimiento del software a largo plazo.

> **Respuesta:**
> La separación reduce el acoplamiento entre los componentes de la aplicación. Al desacoplar la interfaz de usuario de la lógica de negocio, es posible rediseñar completamente la vista (por ejemplo, migrar de un diseño de escritorio a una aplicación web o cambiar estilos gráficos) sin necesidad de modificar el código de las reglas de negocio o cálculos del backend.
> 
> Asimismo, permite que los desarrolladores de backend y los diseñadores de interfaz/frontend trabajen de forma paralela sin interferir entre sí, simplificando la realización de pruebas unitarias sobre la lógica de negocio sin depender de la UI.

---

**17.** Ordene y describa brevemente las tres etapas típicas de prototipado de interfaces, de menor a mayor fidelidad.

> **Respuesta:**
> 
> 1. **Prototipos de Baja Fidelidad (*Paper Prototypes* / Bocetos / Wireframes en papel):**
>    * *Descripción:* Dibujos o esquemas sencillos en papel o pizarra que muestran la distribución general de los elementos visuales. Son muy rápidos y económicos de producir, ideales para validar conceptos iniciales de navegación.
> 2. **Prototipos de Media Fidelidad (*Wireframes* digitales interactivos / *Mockups*):**
>    * *Descripción:* Diseños estructurados creados con herramientas digitales (como Figma o Balsamiq). Incluyen una navegación básica con botones interactivos pero sin estilos gráficos pulidos ni lógica de backend real.
> 3. **Prototipos de Alta Fidelidad (*Prototypes* funcionales):**
>    * *Descripción:* Simulaciones completas y visualmente idénticas a la aplicación final (incluyen colores, tipografías, animaciones e interacciones de datos reales o simulados), utilizadas para pruebas de usabilidad avanzadas con usuarios reales antes de la entrega final.

---

## Cuadro de clasificación

Clasifique cada elemento según el paradigma de diseño al que pertenece principalmente, marcando con una X la columna correspondiente.

| Elemento | Estructurado | Orientado a objetos | Ambos |
|---|---|---|---|
| Diagrama de estructura (structure chart) | **X** | | |
| Diagrama de clases UML | | **X** | |
| Tarjeta CRC | | **X** | |
| PDL / pseudocódigo | | | **X** |
| Diagrama de secuencia | | **X** | |
| DFD (Diagrama de Flujo de Datos) | **X** | | |

---

## Cuadro de relación

Relacione cada concepto de la columna A con su definición correspondiente de la columna B, escribiendo en la tercera columna la letra que corresponda.

| Columna A | Columna B | Respuesta |
|---|---|---|
| **1. Encapsulamiento** | **a.** Los elementos de un módulo están fuertemente relacionados y contribuyen a una única tarea | **c** |
| **2. Herencia** | **b.** Grado de independencia entre los módulos de un sistema | **d** |
| **3. Polimorfismo** | **c.** Los datos y las operaciones que los manipulan se agrupan en una unidad, protegiendo el estado interno | **e** |
| **4. Cohesión** | **d.** Una clase especializa a otra, reutilizando y extendiendo su estructura y comportamiento | **a** |
| **5. Acoplamiento** | **e.** Objetos de distintas clases responden de forma distinta a un mismo mensaje | **b** |

---
*— Fin del ejercitario resuelto —*

```