# Resolución del Ejercitario — Unidad 4: Diseño del Software

**Materia:** Ingeniería de Software 1  
**Unidad:** 4 — Diseño del Software

---

# Tema 1 — Actividad del diseño del software y sus objetivos

## 1. Diferencia entre diseño arquitectónico y diseño detallado

### Diseño Arquitectónico (Macro)

Se ocupa de definir la organización general del sistema. Determina cuáles serán los componentes principales, cómo se comunican entre sí y qué tecnologías o patrones se utilizarán.

**Ejemplo (Sistema de reservas de vuelos):**
Diseñar una solución compuesta por una aplicación web, un conjunto de servicios para gestionar usuarios, reservas y pagos, y una base de datos central para almacenar la información.

### Diseño Detallado (Micro)

Se enfoca en la construcción interna de cada componente definido en la arquitectura. Incluye clases, métodos, algoritmos y estructuras de datos concretas.

**Ejemplo (Sistema de reservas de vuelos):**
Definir la clase `Vuelo`, sus atributos, los métodos necesarios para reservar asientos y el algoritmo utilizado para validar disponibilidad y evitar reservas duplicadas.

---

## 2. Verdadero o Falso

**FALSO**

**Justificación:**  
En diseño de software rara vez existe una única solución correcta. Habitualmente se deben equilibrar distintos atributos de calidad, como rendimiento, mantenibilidad, seguridad o costo. Por ello, varias alternativas pueden ser válidas, dependiendo de las prioridades del proyecto.

---

# Tema 2 — Técnicas de modularización

## 3. Criterio de ocultamiento de información de Parnas

El principio de ocultamiento de información propone que cada módulo debe esconder sus detalles internos de implementación y mostrar únicamente una interfaz clara para ser utilizada por otros módulos.

Esto significa que aspectos susceptibles de cambiar, como algoritmos, formatos de almacenamiento o estructuras de datos internas, deben permanecer encapsulados.

### Impacto en cambios futuros

Si la implementación interna cambia, los demás módulos no necesitan modificarse mientras la interfaz pública siga siendo la misma. Esto reduce dependencias y simplifica el mantenimiento del sistema.

---

## 4. Descomposición Top-Down vs. Bottom-Up

| Enfoque | Ventaja | Desventaja |
|----------|----------|----------|
| **Top-Down** (de lo general a lo particular) | Permite centrarse primero en los objetivos globales y en los requerimientos del usuario. | Algunos componentes complejos pueden descubrirse demasiado tarde. |
| **Bottom-Up** (de lo particular a lo general) | Facilita reutilizar componentes existentes y validar módulos básicos desde etapas tempranas. | Existe el riesgo de perder de vista la visión global del sistema. |

---

## 5. Modularización por Tipos de Datos Abstractos (TDA) — Sistema de Biblioteca

### Módulo: `TDA_Libro`

**Responsabilidad:**  
Representar un libro y administrar su estado dentro de la biblioteca.

**Interfaz pública:**

- `crearLibro(isbn, titulo, autor)`
- `consultarEstado(libro)`
- `prestar(libro)`
- `registrarDevolucion(libro)`

### Módulo: `TDA_Prestamo`

**Responsabilidad:**  
Gestionar los préstamos realizados a los usuarios.

**Interfaz pública:**

- `crearPrestamo(usuario, isbn, fechaLimite)`
- `calcularRecargo(prestamo, fechaActual)`
- `cerrarPrestamo(prestamo)`

---

# Tema 3 — Notaciones de diseño

## 6. Diagrama de estructura vs. Diagrama de clases UML

### Información que muestra un Diagrama de Estructura

- Dependencias jerárquicas entre módulos.
- Flujo de información y llamadas entre componentes.
- Organización funcional del sistema.

### Información que muestra un Diagrama de Clases UML

- Clases, atributos y métodos.
- Relaciones de herencia.
- Asociaciones, agregaciones y composiciones.
- Interfaces y conceptos propios de la orientación a objetos.

---

## 7. Algoritmo en PDL (Pseudocódigo)

```text
ALGORITMO CalcularPromedio

    suma <- 0
    cantidad <- 0

    PARA CADA nota EN listaNotas HACER
        SI nota != NULO ENTONCES
            suma <- suma + nota
            cantidad <- cantidad + 1
        FIN SI
    FIN PARA

    SI cantidad > 0 ENTONCES
        promedio <- suma / cantidad
    SINO
        promedio <- 0
    FIN SI

    RETORNAR promedio

FIN ALGORITMO
```

---

## 8. Completar enunciado

> El diagrama UML de **secuencia** representa el intercambio de mensajes entre objetos durante la ejecución de un caso de uso, mientras que el diagrama de **clases** modela la estructura permanente del sistema.

---

# Tema 4 — Paradigma Orientado a Objetos

## 9. Conceptos fundamentales y ejemplos

### Encapsulamiento

Consiste en proteger el estado interno de un objeto y controlar su acceso mediante métodos definidos.

**Ejemplo:**  
Una clase `CuentaBancaria` mantiene el saldo como atributo privado y solo permite modificarlo mediante operaciones controladas.

### Herencia

Permite crear nuevas clases a partir de otras existentes, reutilizando características comunes.

**Ejemplo:**  
Las clases `Automovil` y `Motocicleta` pueden derivar de una clase general `Vehiculo`.

### Polimorfismo

Permite que diferentes clases respondan de forma distinta ante una misma operación.

**Ejemplo:**  
Diversos tipos de documento implementan un método `exportar()`, pero cada uno genera un formato diferente.

---

## 10. AOO vs. DOO y clases de solución

### Análisis Orientado a Objetos (AOO)

Busca comprender el problema que debe resolver el sistema, identificando conceptos y entidades del negocio.

### Diseño Orientado a Objetos (DOO)

Se enfoca en definir cómo se implementará técnicamente la solución.

### Clases de solución

Aparecen principalmente durante el diseño e incluyen elementos como:

- Controladores.
- Servicios.
- Adaptadores.
- Repositorios.
- Componentes de acceso a datos.

---

## 11. Tarjeta CRC — Clase `Factura`

| Responsabilidades | Colaboradores |
|----------|----------|
| Calcular importes, impuestos y descuentos. | `ItemFactura` |
| Gestionar el estado de la factura. | `Cliente` |
| Enviar información a organismos fiscales o servicios externos. | `ServicioFacturacionElectronica` |

---

## 12. Análisis de sustantivos y verbos

### Sustantivos candidatos a clases

- `Cliente`
- `Pedido`
- `Item`
- `Vendedor`

### Verbos candidatos a operaciones

- `realizar` → operación relacionada con la creación de pedidos.
- `aprobar` → operación vinculada al vendedor o al pedido.
- `compuesto por` → relación entre Pedido e Ítem.

---

## 13. Principio de Sustitución de Liskov (LSP)

### Definición

Una subclase debe poder utilizarse en cualquier lugar donde se espere una instancia de la clase padre sin alterar el comportamiento esperado del sistema.

### Ejemplo de violación

Supongamos una clase `Rectangulo` que permite modificar ancho y alto de forma independiente.

Si una clase `Cuadrado` hereda de ella y fuerza que ambos valores sean iguales, podría generar resultados inesperados cuando sea utilizada como si fuera un rectángulo común.

Esto rompe las expectativas del código cliente y viola el principio de sustitución.

---

## 14. Verdadero o Falso

**VERDADERO**

**Justificación:**  
La sobrescritura de métodos permite que una subclase proporcione una implementación específica para un comportamiento heredado, adaptándolo a sus necesidades particulares.

---

# Tema 5 — Diseño de la interfaz de usuario

## 15. Heurísticas de Nielsen en un formulario de registro

### 1. Visibilidad del estado del sistema

Mostrar mensajes o indicadores que informen continuamente al usuario qué está ocurriendo.

**Ejemplo:** indicador de fortaleza de contraseña o mensaje de validación del correo electrónico.

### 2. Prevención de errores

Evitar que el usuario cometa errores antes de que ocurran.

**Ejemplo:** impedir enviar el formulario mientras existan campos obligatorios vacíos.

### 3. Reconocimiento antes que recuerdo

Presentar información visible para minimizar la carga de memoria del usuario.

**Ejemplo:** etiquetas descriptivas junto a cada campo y ejemplos de formato.

---

## 16. Separación entre interfaz y lógica de negocio (MVC)

Separar la interfaz de usuario de la lógica del negocio aporta varias ventajas:

- Reduce el acoplamiento entre componentes.
- Facilita el mantenimiento.
- Permite reutilizar la lógica con distintas interfaces.
- Favorece las pruebas automáticas.
- Posibilita que equipos diferentes trabajen simultáneamente.

---

## 17. Etapas del prototipado

### Baja fidelidad

Bocetos simples realizados rápidamente para explorar ideas y flujos de navegación.

### Media fidelidad

Prototipos digitales con interacción básica que permiten evaluar la estructura y la usabilidad.

### Alta fidelidad

Representaciones muy cercanas al producto final, incluyendo diseño visual y comportamiento detallado.

---

# Cuadro de clasificación

| Elemento | Estructurado | Orientado a Objetos | Ambos |
|----------|:----------:|:----------:|:----------:|
| Diagrama de estructura | X | | |
| Diagrama de clases UML | | X | |
| Tarjeta CRC | | X | |
| PDL / Pseudocódigo | | | X |
| Diagrama de secuencia | | X | |
| DFD (Diagrama de Flujo de Datos) | X | | |

---

# Cuadro de relación

| Columna A | Columna B | Respuesta |
|----------|----------|:----------:|
| Encapsulamiento | Los datos y operaciones se agrupan para proteger el estado interno. | c |
| Herencia | Una clase deriva de otra reutilizando comportamiento y estructura. | d |
| Polimorfismo | Distintas clases responden de forma diferente al mismo mensaje. | e |
| Cohesión | Los elementos de un módulo colaboran en una misma responsabilidad. | a |
| Acoplamiento | Nivel de dependencia existente entre módulos. | b |
