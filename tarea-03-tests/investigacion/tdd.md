# Test Driven Development (TDD)

## 1. ¿Qué es TDD?

Test Driven Development (TDD) es una metodología de desarrollo de software en la que las pruebas se escriben antes de implementar la funcionalidad que se quiere construir.

La idea principal es definir primero cuál debe ser el comportamiento esperado del software y convertir esa expectativa en una prueba automatizada. Después se implementa únicamente el código necesario para lograr que esa prueba pase.

TDD normalmente se representa mediante el ciclo **Red - Green - Refactor**:

- **Red:** se escribe una prueba que representa el comportamiento esperado. La prueba falla porque la funcionalidad todavía no existe o no cumple con ese comportamiento.
- **Green:** se implementa el código mínimo necesario para hacer que la prueba pase.
- **Refactor:** una vez que la funcionalidad funciona correctamente, se mejora la estructura interna del código sin cambiar su comportamiento.

Una forma sencilla de entenderlo es que en la etapa Red se define mediante una prueba qué queremos que haga el sistema. En Green se programa la solución hasta obtener el resultado esperado, y en Refactor se mejora el "cómo" sin modificar el "qué".

Por esta razón, TDD no es únicamente una técnica para encontrar errores. También funciona como una forma de diseñar software a partir de comportamientos concretos y verificables.

## 2. ¿Cuáles son las ventajas de TDD?

Una de las principales ventajas de TDD es que obliga al desarrollador a pensar primero en el comportamiento esperado antes de concentrarse en la implementación.

Esto ayuda a reducir ambigüedades porque antes de escribir el código se debe tener claro qué resultado se espera obtener.

Otra ventaja es que favorece la creación de código modular. Si una función, clase o componente debe probarse de manera aislada, normalmente es necesario mantener responsabilidades claras y evitar dependencias innecesarias.

TDD también crea una red de seguridad para realizar cambios. Cuando una funcionalidad ya cuenta con pruebas automatizadas, estas pueden ejecutarse nuevamente después de modificar o refactorizar el código para comprobar que el comportamiento anterior continúa funcionando.

Entre sus principales ventajas se pueden mencionar:

- Permite detectar errores durante etapas tempranas del desarrollo.
- Ayuda a definir claramente el comportamiento esperado.
- Favorece código modular y con responsabilidades más claras.
- Facilita futuras refactorizaciones.
- Reduce el riesgo de introducir regresiones.
- Genera pruebas automatizadas como parte natural del desarrollo.
- Aumenta la confianza al modificar funcionalidades existentes.
- Facilita el trabajo en equipo al dejar ejemplos ejecutables del comportamiento esperado.

## 3. ¿Cuáles son las limitaciones de TDD?

TDD también presenta limitaciones y no debe considerarse una solución automática para todos los problemas de software.

Una de sus principales dificultades es que requiere disciplina y experiencia. Al inicio puede sentirse más lento, porque antes de implementar una funcionalidad se debe pensar en escenarios de prueba y escribirlos de forma adecuada.

Además, una prueba puede estar técnicamente correcta pero representar mal el requerimiento. Si se define incorrectamente el comportamiento esperado, se puede obtener una prueba en estado Green aunque la solución no responda correctamente a la necesidad real del sistema.

Otra limitación es que TDD puede resultar más complejo en escenarios donde existen muchas dependencias externas, interfaces visuales altamente cambiantes o procesos donde todavía se está explorando cuál será la solución final.

También es importante entender que tener muchas pruebas no significa automáticamente tener software de calidad. Las pruebas deben representar casos relevantes y estar diseñadas correctamente.

Algunas limitaciones son:

- Requiere tiempo inicial para diseñar las pruebas.
- Necesita disciplina por parte del equipo.
- No garantiza que los requisitos estén correctamente definidos.
- Una mala prueba puede validar un comportamiento incorrecto.
- Puede ser difícil de aplicar en ciertas integraciones o interfaces muy cambiantes.
- No sustituye pruebas de integración, pruebas de interfaz ni validaciones manuales cuando estas son necesarias.

## 4. ¿En qué se diferencia TDD de escribir pruebas después de implementar el código?

La principal diferencia se encuentra en el momento en que se crean las pruebas y en el papel que estas tienen durante el desarrollo.

En TDD, la prueba se escribe primero y funciona como una especificación del comportamiento que todavía debe implementarse.

El proceso se puede representar así:

Requerimiento
→ Prueba
→ RED
→ Implementación
→ GREEN
→ REFACTOR

Cuando las pruebas se escriben después de desarrollar la funcionalidad, el proceso normalmente ocurre así:

Requerimiento
→ Implementación
→ Prueba
→ Validación

Las dos estrategias pueden producir pruebas útiles, pero existe una diferencia importante.

En TDD, las pruebas pueden influir directamente en la forma en que se diseña el código desde el inicio. En cambio, cuando se agregan después, la arquitectura y las decisiones principales de implementación ya existen y las pruebas se utilizan principalmente para verificar lo construido.

Por ejemplo, encontrar pruebas automatizadas dentro de un proyecto no significa automáticamente que ese proyecto haya sido desarrollado utilizando TDD. Para demostrar TDD tendría que existir evidencia de que las pruebas fueron escritas antes de la implementación y que se siguió el ciclo Red-Green-Refactor.

## 5. ¿Cómo contribuye TDD a la calidad del software?

TDD contribuye a la calidad del software porque introduce ciclos cortos de validación durante el proceso de desarrollo.

En lugar de construir una funcionalidad completa y descubrir errores al final, se trabaja mediante pequeños comportamientos comprobables. Cada prueba permite verificar que una parte específica del sistema funciona como se espera.

También favorece la mantenibilidad, porque un código diseñado para poder probarse normalmente tiende a tener responsabilidades más claras y menor acoplamiento.

Otro beneficio importante aparece durante la refactorización. Si el comportamiento ya está protegido por pruebas, es posible modificar la estructura interna del código y volver a ejecutar los tests para comprobar que los resultados siguen siendo correctos.

Esto permite distinguir entre dos aspectos:

- **Qué hace el software:** comportamiento esperado.
- **Cómo está construido:** implementación interna.

Durante un refactor se puede modificar el "cómo", mientras las pruebas ayudan a comprobar que el "qué" permanece igual.

TDD también puede mejorar el trabajo en equipo, porque las pruebas sirven como ejemplos ejecutables de reglas y comportamientos importantes del sistema.

En resumen, TDD puede contribuir a:

- Detectar defectos de forma temprana.
- Evitar regresiones.
- Mejorar la mantenibilidad.
- Facilitar refactorizaciones.
- Promover componentes más pequeños y comprobables.
- Documentar comportamientos importantes mediante pruebas.
- Aumentar la confianza del equipo al realizar cambios.

## Relación con el proyecto EcoWash

En EcoWash existen actualmente pruebas automatizadas y una estrategia de Page Object Model implementada en el trabajo relacionado con EC-40.

Sin embargo, durante la revisión del historial del proyecto no se encontró evidencia suficiente para afirmar que esa implementación haya sido desarrollada utilizando TDD.

El componente `ContactForm` y su lógica ya existían antes de que se agregaran las pruebas correspondientes. Posteriormente se incorporaron las pruebas, la configuración de Vitest y la estrategia POM.

Por esta razón, en este trabajo se diferencia entre:

- **Tener pruebas automatizadas**, y
- **Haber desarrollado utilizando TDD**.

Esta diferencia es importante porque TDD no se determina únicamente observando que las pruebas actuales están en estado exitoso, sino analizando el proceso mediante el cual fueron creadas.

## Conclusión personal

TDD puede entenderse como una forma de convertir primero una expectativa en una prueba y utilizar esa prueba para guiar la implementación.

El ciclo Red-Green-Refactor permite trabajar de manera incremental:

- **Red:** definir mediante una prueba lo que se espera obtener.
- **Green:** implementar la solución mínima necesaria para alcanzar ese resultado.
- **Refactor:** mejorar la forma en que está construida la solución sin modificar el comportamiento conseguido.

Lo más importante es entender que TDD no busca generar errores intencionalmente, sino definir primero una condición verificable antes de construir la solución que debe satisfacerla.
