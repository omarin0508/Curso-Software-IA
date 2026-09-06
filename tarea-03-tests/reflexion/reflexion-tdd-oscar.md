# Reflexión personal sobre TDD — Oscar

Al estudiar TDD entendí que este tipo de metodología está muy orientada a la **sostenibilidad y mantenibilidad del software**. No se trata solamente de crear pruebas para comprobar si algo funciona, sino de establecer un proceso que permita desarrollar, validar y mejorar continuamente una solución.

El propio ciclo **Red-Green-Refactor** muestra esta idea. Para mí, la etapa **Red** no significa crear errores intencionalmente. Primero tenemos claro qué queremos conseguir y cuáles son las condiciones o partes que deberían producir ese resultado. Ese comportamiento esperado se escribe como una prueba y, como la solución todavía no ha sido implementada, la prueba se encuentra naturalmente en estado rojo.

Después viene **Green**, donde se implementa el código necesario para articular esas partes y conseguir el resultado esperado. En este punto ya no basta con tener una idea de cómo debería funcionar la solución: la prueba permite comprobar de manera concreta que la implementación realmente produce el comportamiento que habíamos definido.

Finalmente aparece **Refactor**, que me parece uno de los conceptos más importantes porque entra directamente en el **cómo está construida la solución**. Si el comportamiento ya funciona, podemos mejorar la estructura, simplificar código, reducir duplicaciones o separar mejor las responsabilidades sin cambiar el resultado esperado. Las pruebas permiten comprobar que esas mejoras no hayan roto lo que ya funcionaba.

Por eso entiendo TDD como un proceso cíclico de mejora:

**definir el comportamiento → comprobar que falta → implementar → validar → mejorar → volver a validar.**

También considero importante que este método ayuda a darle **rumbo y enfoque al desarrollo**. En lugar de construir primero una solución grande y comprobarla al final, se avanza desde comportamientos definidos hacia implementaciones concretas y verificables. Esto facilita que el software pueda evolucionar y mantenerse con mayor seguridad.

En conclusión, lo que aprendí de TDD es que las pruebas no solamente sirven para detectar errores. También pueden convertirse en una herramienta para **guiar el desarrollo, comprobar resultados y permitir una mejora constante del código**, manteniendo separado qué debe hacer la solución de cómo está implementada.
