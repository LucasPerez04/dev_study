# Entrega 1: Conceptualización del Proyecto — DevStudy

## 1. Presentación del Proyecto
* **Nombre del sistema:** DevStudy
* **Integrantes del Grupo y Roles:**
  * **Lucas Perez**  
  * **Elias Salinas**
  * **Federico Arrua** 
  * **Luis Saucedo** 
* **Profesor de la Cátedra:** Ing. Fernando Jose Lesme
* **Cliente / Usuario Real:** Estudiantes y docentes de la carrera de Ingeniería de Software.

---

## 2. Definición del Problema

### Contexto y Problema Principal
En el ámbito universitario de las carreras informáticas (como Ingeniería de Software, Ciencias de la Computación o Análisis de Sistemas), el proceso de aprendizaje enfrenta una dispersión y fragmentación constante de las herramientas y recursos de estudio. Actualmente, los estudiantes deben recurrir a múltiples plataformas externas e independientes para cubrir sus necesidades académicas cotidianas:

* **Dispersión de materiales:** Contenidos teóricos, ejercitarios, diapositivas y guías distribuidos de forma no centralizada (carpetas compartidas, correo electrónico, chats de mensajería).
* **Falta de seguimiento del progreso académico:** Inexistencia de un entorno único que permita a los alumnos medir su avance por materia, visualizar temas pendientes o autoevaluarse.
* **Canales de comunicación no estructurados:** Consultas y debates sobre código o ejercicios que se pierden en grupos de chat informales, dificultando la retroalimentación oportuna por parte de los profesores o auxiliares.
* **Dificultad en la gestión de prácticas de programación:** Ausencia de una vía integrada donde el docente pueda centralizar ejercicios prácticos y los estudiantes puedan abordarlos de forma guiada y colaborativa.

### Impacto y Consecuencias
Esta fragmentación genera:
1. **Pérdida de tiempo y desorganización** en los estudiantes al intentar recopilar el material necesario para preparar exámenes y entregas.
2. **Desmotivación y mayor tasa de deserción** en materias con alta curva de aprendizaje técnico, al no contar con un acompañamiento centralizado y fluido.
3. **Carga administrativa adicional para el cuerpo docente**, que debe atender consultas repetitivas por canales informales y carece de visibilidad clara sobre las dificultades del alumnado.

### Necesidad de la Solución
Existe la necesidad explícita de contar con una **plataforma web integral, centralizada y orientada al área informática (DevStudy)**, que unifique la gestión de recursos de estudio, el seguimiento individual de contenidos y la interacción académica entre docentes y estudiantes de la carrera.

```

---

## 3. Propósito y Objetivos

### Propósito del Proyecto
El propósito de **DevStudy** es dotar a la comunidad académica del área de informática de la **Universidad Católica "Nuestra Señora de la Asunción"** de un entorno digital centralizado, moderno y eficiente que optimice el proceso de enseñanza-aprendizaje. La plataforma busca acompañar la trayectoria estudiantil facilitando la gestión de materiales académicos, el seguimiento del progreso individual y la interacción continua entre docentes y alumnos.

---

### Objetivos

#### Objetivo General
Desarrollar e implementar la plataforma web **DevStudy** para centralizar la gestión de contenidos, ejercicios prácticos y consultas académicas de las materias informáticas en la **Universidad Católica "Nuestra Señora de la Asunción"**, mejorando el rendimiento académico y la comunicación institucional durante el periodo académico.

#### Objetivos Específicos
* **Centralizar los recursos académicos:** Proporcionar un repositorio organizado donde los docentes puedan publicar programas de estudio, guías prácticas, ejercicios de programación y material de apoyo por asignatura.
* **Ofrecer seguimiento del progreso estudiantil:** Implementar un panel interactivo que permita a los alumnos visualizar el avance de su plan de estudios, entregas pendientes y nivel de cumplimiento por materia.
* **Fomentar la comunicación estructurada:** Canalizar las dudas, debates teóricos y consultas de código a través de un espacio de discusión dedicado para evitar la dispersión de información en chats informales.
* **Garantizar una experiencia accesible y adaptativa:** Diseñar una interfaz web intuitiva, de rápida carga y compatible con dispositivos móviles y de escritorio para el uso cotidiano de la comunidad de la **UC**.

---

## 4. Alcance del Proyecto
*(Sección asignada a Federico Arrua)*

---

## 5. Interesados (Stakeholders)
*(Sección asignada a Luis Saucedo)*

---

## 6. Justificación y Viabilidad
*(Sección asignada a Luis Saucedo)*

---

## 7. Visión General de la Solución
*(Sección asignada a Federico Arrua)*

---

## 8. Glosario de Términos
*(Sección asignada a Luis Saucedo)*

---

## 9. Riesgos Iniciales y Mitigación

| Riesgo Identificado | Tipo / Categoría | Nivel | Estrategia de Mitigación |
| :--- | :--- | :--- | :--- |
| **Curva de aprendizaje del stack (React / Node.js)** | Técnico | Medio | Realización de talleres internos y uso de plantillas base (*boilerplates*) para agilizar la puesta en marcha. |
| **Disponibilidad acotada de tiempo de los integrantes** | Planificación | Alto | Definición de un alcance V1.0 bien delimitado y asignación clara de tareas mediante asignaciones de Git. |
| **Incompatibilidad o fallos en el despliegue de GitHub Pages** | Infraestructura | Bajo | Configuración desde el inicio del archivo `.nojekyll` e integración continua probada en `/docs`. |
| **Desalineación con las expectativas de la cátedra** | Alcance / Cliente | Medio | Revisiones periódicas del documento de conceptualización con el Ing. Fernando Jose Lesme. |

---

## 10. Selección Tecnológica Preliminar

* **Frontend — React:** Se elige por su arquitectura basada en componentes reutilizables, lo que facilita el desarrollo de una interfaz de usuario modular, declarativa y de alto rendimiento.
* **Backend — Node.js (con Express):** Permite mantener un único lenguaje de programación (JavaScript) en todo el stack (*full-stack*), facilitando la integración con la base de datos y ofreciendo alta eficiencia en el manejo de peticiones asíncronas.
* **Base de Datos — PostgreSQL:** Se selecciona un motor relacional sólido, confiable y de código abierto para garantizar la integridad referencial y el modelado estructurado de usuarios, cursos y recursos didácticos.
