# 🥋 Kata 01: Fundamentos del Diseño

**Cátedra:** Algoritmos y Estructuras de Datos II  
**Institución:** ISFT 151 - Analista de Sistemas  
**Profesor:** José Luis Oemig  

Este documento sintetiza los conceptos teóricos y prácticos abordados en el primer Kata. El enfoque central radica en establecer los criterios arquitectónicos necesarios para la construcción de software robusto, escalable y tolerante al cambio.

---

## 🏗️ 1. Fundamentos Teóricos

El diseño de sistemas se evalúa a través de tres pilares fundamentales:

* **Paradigmas de Programación:** Transición del flujo imperativo lineal hacia el paradigma de Orientación a Objetos. Se enfatiza la orquestación de mensajes y la correcta gestión de estados complejos para modelar el dominio.
* **Arquitecturas:** Diseño orientado a fronteras. El objetivo técnico es aislar las reglas de negocio de los detalles de implementación (frameworks, bases de datos) para garantizar la longevidad y mantenibilidad del sistema.
* **Memoria y Datos:** Análisis de las estructuras fundamentales. Se evalúa el balance entre la rigidez estructural de un Array contiguo y la elasticidad de una Lista Dinámica.

---

## 🔬 2. Laboratorio POO: Inversión de Dependencias (DIP)

Análisis comparativo de acoplamiento a nivel arquitectónico.

### ❌ Modelo Tradicional (Alto Acoplamiento)
El flujo de control y las dependencias van en la misma dirección. Un caso de uso (`CreateUserUseCase`) depende directamente de un repositorio de datos concreto (`SqlRepository`). 
* **Problema:** Una modificación estructural en el motor de base de datos rompe directamente la lógica de negocio.

### ✅ Modelo Invertido (Aplicación de DIP)
Se interpone una abstracción. El caso de uso ahora depende únicamente de una interfaz (`«Interface» IRepository`), y es el repositorio de datos concreto el que debe implementar dicha abstracción.
* **Solución:** El detalle técnico depende de la abstracción. Se logra la independencia total de la capa de dominio.

> 💡 **Reflexión del Maestro:**
> *"Un arquitecto de software no dibuja líneas; dibuja fronteras. Al invertir la dependencia, protegemos la esencia del sistema contra la marea constante del cambio tecnológico."*

---

## ⚔️ 3. Dinámica Grupal: Kumites Técnicos

Debates analíticos contrastando soluciones frente a requerimientos específicos:

### Kumite #1: Paradigma Estructurado vs. Orientado a Objetos
* **Estructurado:** Destaca por su alta eficiencia en el uso de recursos, cercanía al hardware y un flujo de ejecución previsible.
* **Objetos (POO):** Indispensable para sistemas con alta tasa de mutación. Permite el encapsulamiento del cambio, oculta la complejidad estructural y facilita la extensibilidad mediante polimorfismo.

### Kumite #2: Arquitectura Estándar vs. Arquitectura Limpia
* **Estándar:** Recomendada para MVPs (Minimum Viable Products). Presenta una estructura directa, menor costo de desarrollo inicial y una curva de aprendizaje mínima.
* **Limpia (Clean):** Prioriza el largo plazo. Permite el testeo unitario aislado de los componentes, independiza el código de las tecnologías de turno y desacopla por completo las reglas del negocio.

### Kumite #3: Estructuras en Memoria (Array vs. Lista Dinámica)
Aplicado a un sistema con límites estrictos (ej. turnos médicos).
* **Array (Estático):** Garantiza un acceso posicional inmediato en tiempo constante O(1). Hace un uso eficiente de la memoria caché del hardware y minimiza el overhead en RAM.
* **Lista (Dinámica):** Ofrece inserciones y eliminaciones rápidas sin requerir memoria contigua, adaptándose de manera elástica a las necesidades de almacenamiento en tiempo de ejecución.