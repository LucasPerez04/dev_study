# Resolución del Ejercitario — Unidad 4: Diseño del Software

**Materia:** Ingeniería de Software 1  
**Unidad:** 4 — Diseño del software  

---

## Tema 1 — Actividad del diseño del software y sus objetivos

### 1. Diferencia entre diseño arquitectónico y diseño detallado

* **Diseño Arquitectónico (Macro):** Define la estructura global del sistema, identificando sus módulos principales o subsistemas, la relación entre ellos y las tecnologías clave.
  * *Ejemplo (Reserva de Vuelos):* Definir una arquitectura de 3 capas compuesta por un cliente web/móvil, una API Gateway con microservicios para *Autenticación*, *Reservas* y *Pagos*, y una base de datos relacional para el almacenamiento persistente.
* **Diseño Detallado (Micro):** Especifica la estructura interna de cada componente, incluyendo algoritmos, estructuras de datos, firmas de métodos e interfaces concretas.
  * *Ejemplo (Reserva de Vuelos):* Diseñar la clase `Vuelo` con sus atributos privados (`codigo`, `asientosDisponibles`), la firma de sus métodos (`reservarAsiento()`, `validarDisponibilidad()`) y el pseudocódigo del algoritmo que bloquea temporalmente las plazas durante el checkout.

### 2. Verdadero o Falso

**FALSO**

**Justificación:** El diseño de software implica evaluar múltiples trade-offs (compromisos) entre atributos de calidad en conflicto (por ejemplo, rendimiento vs. mantenibilidad, o costo vs. disponibilidad). Por esta razón, no existe una única solución "óptima", sino un abanico de alternativas válidas donde la mejor opción dependerá de los requerimientos no funcionales y del contexto específico del proyecto.

---

## Tema 2 — Técnicas de modularización

### 3. Criterio de ocultamiento de información de Parnas

El principio de ocultamiento de información (*Information Hiding*) de David Parnas establece que cada módulo debe ocultar a los demás sus decisiones de diseño internas y propensas al cambio (estructuras de datos, algoritmos complejos, detalles del hardware o de la base de datos), exponiendo únicamente una interfaz pública y estable.

**Impacto en cambios futuros:** Al aislar los detalles de implementación dentro del módulo, cualquier cambio futuro en dicha lógica (por ejemplo, cambiar la forma en que se almacenan o procesan los datos) no afecta a otros módulos del sistema, reduciendo así el efecto dominó y el costo del mantenimiento.

### 4. Descomposición Top-Down vs. Bottom-Up

| Enfoque | Ventaja | Desventaja |
|---|---|---|
| **Top-Down** *(De lo general a lo particular)* | Permite centrarse desde el principio en los requerimientos del usuario y en la estructura lógica global del sistema. | Puede retrasar la prueba y validación de componentes de bajo nivel clave o técnicamente complejos. |
| **Bottom-Up** *(De lo particular a lo general)* | Facilita la reutilización de código y permite probar e implementar los módulos base y utilitarios tempranamente. | Existe el riesgo de construir componentes que no se alineen adecuadamente con las necesidades del sistema global. |

### 5. Modularización por Tipos de Datos Abstractos (TDA) — Gestión de Biblioteca

#### Módulo 1: `TDA_Libro`
* **Descripción:** Encapsula la información y lógica asociada a un libro individual.
* **Interfaz pública:**
  * `crearLibro(isbn: String, titulo: String, autor: String): Libro`
  * `obtenerEstado(libro: Libro): EstadoLibro`
  * `prestar(libro: Libro): Boolean`
  * `devolver(libro: Libro): Boolean`

#### Módulo 2: `TDA_Prestamo`
* **Descripción:** Administra la transacción del préstamo de ejemplares a los usuarios.
* **Interfaz pública:**
  * `registrarPrestamo(idUsuario: String, isbn: String, fechaDevolucion: Date): Prestamo`
  * `calcularMulta(prestamo: Prestamo, fechaActual: Date): Double`
  * `finalizarPrestamo(prestamo: Prestamo): Boolean`

---

## Tema 3 — Notaciones de diseño

### 6. Diagrama de estructura vs. Diagrama de clases UML

* **Información del Diagrama de Estructura que NO transmite el Diagrama de Clases:**
  * La jerarquía de invocación entre módulos procedurales/funciones.
  * El flujo y paso de datos explícito (*data couples*) y parámetros de control (*control flags*) entre componentes durante la ejecución.
* **Información del Diagrama de Clases UML que NO transmite el Diagrama de Estructura:**
  * Conceptos del paradigma orientado a objetos como herencia, polimorfismo, interfaces y encapsulamiento.
  * La estructura estática basada en atributos y operaciones agrupados en clases, así como relaciones avanzadas de agregación y composición.

### 7. Algoritmo en PDL (Pseudocódigo)

```text
ALGORITMO CalcularPromedioSinNulos(listaCalificaciones)
    ENTRADA: listaCalificaciones (lista de números reales o nulos)
    SALIDA: promedio (número real)

    INICIO
        sumaTotal <- 0
        contadorValidos <- 0

        PARA CADA calificacion EN listaCalificaciones HACER
            SI calificacion NO ES NULO ENTONCES
                sumaTotal <- sumaTotal + calificacion
                contadorValidos <- contadorValidos + 1
            FIN SI
        FIN PARA

        SI contadorValidos > 0 ENTONCES
            promedio <- sumaTotal / contadorValidos
        SINO
            promedio <- 0
            ESCRIBIR "No existen calificaciones válidas para calcular el promedio."
        FIN SI

        RETORNAR promedio
    FIN
```

### 8. Completar enunciado

> El diagrama UML de **secuencia** documenta la interacción dinámica entre objetos concretos a lo largo del tiempo, mientras que el diagrama de **clases** documenta la estructura estática de clases, atributos y relaciones.

---

## Tema 4 — El paradigma orientado a objetos (Análisis y Diseño OO)

### 9. Conceptos de OO y ejemplos

* **Encapsulamiento:** Ocultar el estado interno de un objeto permitiendo su modificación únicamente mediante métodos públicos expuestos.
  * *Ejemplo:* Una clase `CuentaBancaria` que mantiene el atributo `saldo` en privado y solo permite modificarlo usando `depositar(monto)` o `retirar(monto)`, validando que no se extraiga más dinero del saldo disponible.
* **Herencia:** Capacidad de una clase (subclase) de derivar de otra (superclase), adquiríendo sus atributos y comportamientos para extenderlos o especializarlos.
  * *Ejemplo:* Una superclase `Vehiculo` con atributos como `marca` y `velocidadMaxima`, de la cual heredan `Automovil` (agrega `numeroPuertas`) y `Motocicleta` (agrega `cilindrada`).
* **Polimorfismo:** Propiedad que permite invocar el mismo método en distintos objetos y que cada uno responda de manera específica según su propia implementación.
  * *Ejemplo:* Una interfaz `Documento` con el método `exportar()`. Las clases `DocumentoPDF` y `DocumentoExcel` implementan `exportar()`, generando formatos de archivo totalmente distintos tras la misma llamada.

### 10. AOO vs. DOO y Clases de Solución

* **Análisis Orientado a Objetos (AOO):** Se enfoca en comprender e identificar los conceptos del dominio del problema (qué hace el sistema) sin pensar en decisiones tecnológicas.
* **Diseño Orientado a Objetos (DOO):** Se centra en cómo construir la solución técnica, especificando detalles de software, infraestructura y persistencia.
* **¿Dónde aparecen las clases de solución?** Aparecen durante la etapa de **Diseño Orientado a Objetos (DOO)** (por ejemplo, manejadores de bases de datos, controladores de interfaz gráfica o servicios de conexión HTTP).

### 11. Tarjeta CRC — Clase `Factura`

| Clase: `Factura` | |
|---|---|
| **Responsabilidades** | **Colaboradores** |
| 1. Calcular el total a pagar aplicando impuestos y descuentos. | `ItemFactura` |
| 2. Mantener y actualizar el estado de emisión del comprobante. | `Cliente` |
| 3. Transmitir los datos al servicio fiscal correspondiente. | `ServicioFacturacionElectronica` |

### 12. Análisis de sustantivos / verbos

**Texto:** *"El sistema debe permitir que un Cliente realice un Pedido compuesto por uno o más Ítems, y que un Vendedor apruebe dicho Pedido."*

* **Sustantivos (Candidatos a Clases):**
  * `Cliente` $\rightarrow$ **Clase**
  * `Pedido` $\rightarrow$ **Clase**
  * `Ítem` $\rightarrow$ **Clase**
  * `Vendedor` $\rightarrow$ **Clase**
  * *(Sistema: se descarta por ser el sistema global).*
* **Verbos (Candidatos a Operaciones / Relaciones):**
  * `realice` $\rightarrow$ **Operación** (`Cliente.realizarPedido()` o `Pedido.crear()`)
  * `compuesto por` $\rightarrow$ **Relación de composición** (entre `Pedido` e `Ítem`)
  * `apruebe` $\rightarrow$ **Operación** (`Vendedor.aprobarPedido()` o `Pedido.aprobar()`)

### 13. Principio de Sustitución de Liskov (LSP) y Contraejemplo

**Explicación:** LSP establece que los objetos de una subclase deben poder sustituir a los objetos de la superclase sin alterar el correcto funcionamiento ni las propiedades esperadas del programa.

**Contraejemplo de violación:**
* Superclase `Rectangulo` con métodos `setAncho(a)` y `setAlto(h)`.
* Subclase `Cuadrado` que hereda de `Rectangulo`. Al requerir lados iguales, sobreescribe `setAncho(a)` y `setAlto(h)` para modificar ambas dimensiones al mismo tiempo.
* *Violación:* Si una función cliente recibe un `Rectangulo` y llama a `r.setAncho(5)` seguido de `r.setAlto(10)`, esperará que el área sea $50$. Si se le pasa una instancia de `Cuadrado`, el área terminará siendo $100$, rompiendo el comportamiento esperado y violando LSP.

### 14. Verdadero o Falso

**VERDADERO**

**Justificación:** El polimorfismo mediante sobrescritura (*overriding*) permite que cada subclase redefina el cuerpo de un método heredado de la superclase para adaptar la respuesta del objeto a sus requerimientos particulares.

---

## Tema 5 — Diseño de la interfaz del usuario

### 15. Heurísticas de Nielsen aplicadas a un Formulario de Registro

1. **Visibilidad del estado del sistema:**
   * *Aplicación:* Indicar visualmente la fortaleza de la contraseña a medida que se escribe o mostrar un indicador de carga (*spinner*) mientras se verifica si el correo ya existe.
2. **Prevención de errores:**
   * *Aplicación:* Deshabilitar el botón "Registrarse" hasta que los campos obligatorios estén completos y válidos, o restringir la entrada de caracteres en campos numéricos.
3. **Reconocimiento antes que recordar:**
   * *Aplicación:* Usar etiquetas visibles (*labels*) permanentes y sugerencias de formato (*placeholders*) claras en lugar de confiar en que el usuario recuerde las instrucciones.

### 16. Separación entre Interfaz y Lógica de Negocio (MVC)

Esta separación promueve un **bajo acoplamiento**:
* Permite modificar o reemplazar la interfaz de usuario (ej. migrar de una web desktop a una aplicación móvil) sin alterar las reglas de negocio subyacentes.
* Facilita la reutilización de componentes y permite realizar pruebas unitarias sobre la lógica de negocio sin depender de la UI.
* Permite que diseñadores y desarrolladores trabajen de forma paralela sin interferir entre sí.

### 17. Etapas de Prototipado de Interfaces

1. **Baja Fidelidad (Low-Fidelity):** Bocetos simples a mano o *wireframes* conceptuales en papel. Sirven para explorar ideas, distribución de contenido y flujo general rápidamente y con bajo costo.
2. **Media Fidelidad (Mid-Fidelity):** Diseños digitales interactivos en escala de grises. Permiten validar la navegación, estructura y usabilidad básica sin distracciones visuales.
3. **Alta Fidelidad (High-Fidelity):** Maquetas interactivas con colores, tipografías finales y datos realistas. Muestran con precisión el comportamiento y apariencia final de la aplicación antes del desarrollo.

---

## Cuadro de clasificación

| Elemento | Estructurado | Orientado a objetos | Ambos |
|---|:---:|:---:|:---:|
| Diagrama de estructura (*structure chart*) | **X** | | |
| Diagrama de clases UML | | **X** | |
| Tarjeta CRC | | **X** | |
| PDL / pseudocódigo | | | **X** |
| Diagrama de secuencia | | **X** | |
| DFD (Diagrama de Flujo de Datos) | **X** | | |

---

## Cuadro de relación

| Columna A | Columna B | Respuesta |
|---|---|:---:|
| **1. Encapsulamiento** | **c.** Los datos y las operaciones que los manipulan se agrupan en una unidad, protegiendo el estado interno | **c** |
| **2. Herencia** | **d.** Una clase especializa a otra, reutilizando y extendiendo su estructura y comportamiento | **d** |
| **3. Polimorfismo** | **e.** Objetos de distintas clases responden de forma distinta a un mismo mensaje | **e** |
| **4. Cohesión** | **a.** Los elementos de un módulo están fuertemente relacionados y contribuyen a una única tarea | **a** |
| **5. Acoplamiento** | **b.** Grado de independencia entre los módulos de un sistema | **b** |