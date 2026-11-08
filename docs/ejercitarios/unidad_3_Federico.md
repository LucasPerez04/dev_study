# Respuestas — Ejercitario Unidad 03 Test

## Tema 1 · Rigor y formalidad

### 1. Explica con tus propias palabras la diferencia entre "rigor" y "formalidad" en el desarrollo de software. Da un ejemplo de cada uno.

**Respuesta:**

El rigor consiste en trabajar de manera ordenada, precisa y fundamentada, verificando que cada decisión y resultado sea correcto. La formalidad, en cambio, implica utilizar lenguajes, modelos o métodos con reglas matemáticas o sintácticas bien definidas.

**Ejemplo de rigor:** realizar revisiones de código sistemáticas y pruebas exhaustivas antes de publicar una nueva versión.

**Ejemplo de formalidad:** utilizar una especificación formal para describir el comportamiento de un sistema crítico mediante notación matemática.

---

## Tema 2 · Separación de intereses

### 2. ¿Por qué no conviene formalizar por completo todos los aspectos de un proyecto de software? Menciona un caso donde sí valga la pena hacerlo.

**Respuesta:**

No conviene formalizar todo porque el costo, el tiempo y el esfuerzo necesarios pueden ser demasiado elevados en comparación con los beneficios obtenidos. Además, algunos aspectos del proyecto cambian frecuentemente y una formalización excesiva puede dificultar la adaptación.

Un caso donde sí vale la pena formalizar es en sistemas críticos, como software para aeronaves, equipos médicos o centrales nucleares, donde un error puede tener consecuencias graves.

---

## Tema 2 · Separación de intereses

### 3. En tus propias palabras, ¿qué significa "separar intereses" en el diseño de un sistema? Da un ejemplo distinto al visto en clase.

**Respuesta:**

Separar intereses significa dividir un sistema en partes donde cada una se encargue de una responsabilidad específica. De esta manera, los cambios en un aspecto del sistema tienen menor impacto sobre los demás y el software resulta más fácil de comprender y mantener.

**Ejemplo:** en una tienda en línea, se puede separar la gestión de productos, el procesamiento de pagos y el envío de notificaciones por correo en componentes diferentes.

---

### 4. Para una aplicación de reservas de vuelos, identifica al menos tres "intereses" o aspectos distintos que deberían mantenerse separados, y explica brevemente por qué.

**Respuesta:**

1. **Gestión de vuelos:** encargado de consultar horarios, rutas y disponibilidad de asientos.
2. **Procesamiento de pagos:** responsable de validar y procesar las transacciones financieras.
3. **Gestión de usuarios:** encargado de registrar clientes, autenticar usuarios y administrar perfiles.

Estos aspectos deben mantenerse separados porque tienen responsabilidades diferentes y suelen cambiar por motivos distintos. Separarlos reduce el impacto de las modificaciones y facilita el mantenimiento.

---

## Tema 3 · Modularidad

### 5. Explica con tus propias palabras la relación entre modularidad, acoplamiento y cohesión.

**Respuesta:**

La modularidad busca dividir un sistema en componentes independientes. Para lograrlo, cada módulo debe tener **alta cohesión**, es decir, encargarse de tareas relacionadas entre sí, y **bajo acoplamiento**, es decir, depender lo menos posible de otros módulos. Cuanto mayor sea la cohesión y menor el acoplamiento, más fácil será comprender, modificar y mantener el sistema.

---

### 6. Completa el siguiente cuadro indicando si cada situación es un ejemplo de "alto acoplamiento" o de "baja cohesión", y justifica tu respuesta.

| Situación | ¿Acoplamiento o cohesión? | Justificación |
|------------|------------|------------|
| Un módulo de "utilidades" que mezcla validaciones, envío de emails y cálculos financieros | Baja cohesión | Realiza tareas poco relacionadas entre sí. |
| Dos módulos que se llaman constantemente entre sí y comparten variables globales | Alto acoplamiento | Existe una fuerte dependencia entre ambos módulos. |
| Un módulo de "reportes" que además valida los permisos del usuario | Baja cohesión | Combina responsabilidades distintas dentro del mismo módulo. |
| Un módulo de autenticación que solo se encarga de validar credenciales | Alta cohesión | Todas sus funciones están relacionadas con una única responsabilidad. |

---

### 7. ¿Por qué una interfaz bien definida entre módulos reduce el impacto de los cambios internos de cada uno?

**Respuesta:**

Porque los demás módulos solo conocen la interfaz pública y no los detalles internos de implementación. Mientras la interfaz se mantenga estable, es posible modificar el funcionamiento interno de un módulo sin afectar al resto del sistema. Esto facilita la evolución y el mantenimiento del software.

---

## Tema 4 · Abstracción

### 8. Relaciona cada nivel con su descripción.

| Nivel | N.º de descripción |
|---------|---------|
| A. Negocio / Requisitos | 2 |
| B. Diseño / Arquitectura | 3 |
| C. Implementación / Código | 1 |

---

### 9. Da un ejemplo de una situación cotidiana (no necesariamente de software) donde se apliquen distintos niveles de abstracción.

**Respuesta:**

La construcción de una casa.

- **Nivel de negocio o requisitos:** el propietario quiere una casa con tres habitaciones, dos baños y un garaje.
- **Nivel de diseño:** el arquitecto crea los planos y define la distribución de los ambientes.
- **Nivel de implementación:** los albañiles construyen la casa siguiendo los planos y utilizando materiales específicos.

Cada nivel se centra en detalles diferentes del mismo problema.

---

## Tema 5 · Anticipación al cambio

### 10. ¿Qué significa "anticipar el cambio" en el diseño de software? ¿Implica predecir exactamente qué va a cambiar en el futuro?

**Respuesta:**

Anticipar el cambio significa diseñar el sistema de forma que las modificaciones futuras puedan realizarse con un impacto reducido. No implica predecir exactamente qué cambiará, sino identificar las áreas que probablemente evolucionen y prepararlas para adaptarse con facilidad.

---

### 11. Para un sistema de pagos en línea, identifica una parte que probablemente cambie en el futuro y propone cómo aislarla del resto del sistema.

**Respuesta:**

Una parte que probablemente cambie son las plataformas o proveedores de pago, como tarjetas de crédito, billeteras digitales o servicios bancarios.

Para aislar esa variabilidad, se puede crear un módulo o interfaz específica para procesar pagos. De esta manera, si en el futuro se reemplaza un proveedor o se agrega uno nuevo, solo será necesario modificar ese módulo sin afectar al resto del sistema.

---

## Tema 6 · Generalidad

### 12. ¿Cuál es el riesgo de generalizar demasiado una solución? Da un ejemplo concreto de una solución "sobre-generalizada".

**Respuesta:**

El riesgo es aumentar innecesariamente la complejidad del sistema, dificultando su comprensión, desarrollo y mantenimiento. También puede provocar que se invierta tiempo en resolver problemas que nunca llegarán a existir.

**Ejemplo:** desarrollar un sistema de gestión de inventario para una pequeña tienda incluyendo soporte para cientos de tipos de almacenes, monedas y configuraciones internacionales que la empresa nunca utilizará.

---

## Tema 7 · Incrementalidad

### 13. Explica la diferencia entre construir un sistema de forma incremental y construirlo todo de una vez ("big bang").

**Respuesta:**

En el desarrollo incremental, el sistema se construye en pequeñas partes funcionales que se entregan progresivamente. Esto permite recibir retroalimentación temprana, detectar problemas antes y adaptarse a cambios en los requisitos.

En el enfoque "big bang", todo el sistema se desarrolla y entrega al final del proyecto. Esto incrementa el riesgo, ya que los errores o problemas importantes suelen descubrirse recién en etapas avanzadas.

---

### 14. Reflexión final: de los siete principios vistos en la Unidad 3, ¿cuál te parece más difícil de aplicar en la práctica, y por qué?

**Respuesta:**

El principio que considero más difícil de aplicar es la **anticipación al cambio**. Resulta complicado encontrar el equilibrio entre preparar el sistema para futuras modificaciones y evitar una complejidad excesiva. Si se anticipan muy pocos cambios, el sistema puede volverse rígido; pero si se intentan prever demasiados escenarios, se corre el riesgo de crear una solución innecesariamente compleja. Por eso, requiere experiencia y criterio para tomar buenas decisiones de diseño.
