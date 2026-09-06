# Tarea 3 — Tests: Page Object Model y Test Driven Development

## Integrantes

- Oscar Marín
- Kevin [apellido pendiente]

## Introducción

Este trabajo estudia dos temas relacionados con pruebas de software: Page Object Model (POM) y Test Driven Development (TDD). Primero se explican sus conceptos principales, objetivos, ventajas y limitaciones. Luego se analiza cómo estos conceptos se relacionan con la estrategia de pruebas utilizada en el proyecto EcoWash.

Para evitar un análisis únicamente teórico, se utiliza código real de EcoWash como evidencia técnica. En particular, se revisan las pruebas del componente `ContactForm`, el Page Object `ContactFormPage`, la prueba del hook `useContactForm`, la configuración de Vitest y el skill interno de estándares de pruebas.

También se diferencia claramente entre tener pruebas automatizadas y haber desarrollado mediante TDD. Esta distinción es importante porque la existencia de tests no demuestra por sí sola que el proceso haya seguido el ciclo Red-Green-Refactor.

---

# Parte I — Page Object Model (POM)

## 1. ¿Qué es Page Object Model?

Page Object Model (POM) es un patrón utilizado en pruebas automatizadas para crear una capa de abstracción entre los tests y los detalles concretos de una interfaz. En lugar de que cada prueba busque directamente los elementos de la pantalla y repita las mismas acciones, se crea un objeto que representa una página, pantalla o componente.

Ese objeto encapsula elementos, selectores, acciones e interacciones. De esta manera, las pruebas pueden expresar qué comportamiento desean validar sin quedar llenas de detalles técnicos sobre cómo encontrar cada campo o botón.

Aunque POM no es lo mismo que Programación Orientada a Objetos (POO), puede entenderse usando ideas conocidas de POO, como objetos, encapsulación, abstracción y separación de responsabilidades. Por ejemplo, un Page Object puede representar el formulario de contacto y exponer una API clara para usarlo en distintas pruebas.

Ejemplo conceptual:

```text
ContactFormPage
├── nameInput
├── emailInput
├── submitButton
├── fillValidForm()
└── submit()
```

Después, varias pruebas particulares pueden reutilizar ese mismo modelo para validar comportamientos diferentes del formulario.

## 2. ¿Cuál es el objetivo principal?

El objetivo principal de POM es separar las pruebas de los detalles internos de la interfaz. Una prueba debería concentrarse en el comportamiento que quiere verificar, no en repetir selectores, llamadas a librerías de interacción o pasos técnicos de bajo nivel.

Con POM, los detalles de UI quedan centralizados en una clase o módulo especializado. Esto ayuda a evitar repetición, facilita el mantenimiento y mejora la legibilidad de los tests.

## 3. ¿Qué problemas intenta resolver?

POM intenta resolver varios problemas frecuentes en pruebas de interfaz:

- Selectores repetidos en muchos tests.
- Acciones repetidas, como llenar formularios o presionar botones.
- Tests demasiado acoplados a la estructura de la interfaz.
- Cambios de UI que obligan a modificar muchos archivos de prueba.
- Pruebas difíciles de leer porque mezclan intención, búsqueda de elementos e interacción.

Sin POM, un cambio pequeño en una etiqueta, un selector o la forma de interactuar con un elemento puede obligar a actualizar múltiples pruebas. Con POM, ese cambio puede concentrarse en el Page Object.

## 4. Principales características

Las principales características de Page Object Model son:

- Representa una página, pantalla o componente mediante un objeto.
- Encapsula selectores y mecanismos para encontrar elementos.
- Encapsula acciones del usuario, como escribir, seleccionar o hacer clic.
- Expone una API reutilizable para los tests.
- Separa interacción y assertions.
- Permite reutilizar comportamientos comunes en múltiples pruebas.

Una regla importante es que el Page Object no debería contener validaciones con `expect(...)`. Las assertions pertenecen al archivo de test. El Page Object prepara o ejecuta interacciones; el test verifica el resultado.

## 5. Ventajas respecto a pruebas sin POM

Frente a pruebas escritas directamente con selectores e interacciones, POM ofrece varias ventajas.

Primero, mejora la mantenibilidad. Si cambia la forma de localizar un campo, se modifica el Page Object y no todas las pruebas que lo usan. Segundo, favorece la reutilización, porque métodos como `fillValidForm()` o `submit()` pueden usarse en diferentes escenarios. Tercero, mejora la legibilidad, ya que el test puede leerse como una secuencia de comportamiento.

También reduce la duplicación. En lugar de repetir llamadas a `screen.getByLabelText(...)`, `user.type(...)` o `user.click(...)`, esas operaciones quedan encapsuladas en métodos con nombres más cercanos a la intención del usuario.

## 6. Desventajas o limitaciones

POM también tiene limitaciones. Agrega una capa adicional que debe mantenerse, por lo que no siempre se justifica para pruebas muy pequeñas o de lógica pura. Si se usa sin criterio, puede convertirse en sobreingeniería.

Además, un Page Object demasiado grande puede concentrar demasiadas responsabilidades y volverse difícil de mantener. Por eso debe representar una página o componente de forma clara, sin mezclar validaciones ni lógica que corresponde a los tests.

No todas las pruebas necesitan POM. En EcoWash, `useContactForm.test.ts` no utiliza Page Object porque prueba la lógica de un hook mediante `renderHook`, `act` y eventos simulados. No representa una interfaz completa ni necesita localizar elementos visuales. Aplicar POM ahí no aportaría valor y haría la prueba más compleja de lo necesario.

## 7. Relación con principios de diseño

### Responsabilidad Única (SRP)

POM se relaciona con el principio de Responsabilidad Única porque separa responsabilidades dentro del testing. El Page Object se encarga de cómo interactuar con la interfaz, mientras que el archivo de test se concentra en el comportamiento esperado y las assertions.

Esto evita que cada test tenga que conocer todos los detalles de la UI. La prueba puede expresar intención y delegar la interacción al Page Object.

### Reutilización de código

Cuando varias pruebas necesitan llenar el mismo formulario o ejecutar una misma acción, POM permite reutilizar métodos comunes. Por ejemplo, una función como `fillValidForm()` puede servir para pruebas de envío exitoso, validación del payload o reinicio del formulario.

### Mantenibilidad

Si cambia un selector o una etiqueta, el cambio puede hacerse de forma centralizada en el Page Object. Esto reduce el riesgo de errores y evita modificar muchas pruebas por el mismo motivo.

## POM contextualizado en EcoWash

En EcoWash se encontró una implementación real de POM en el archivo `ContactForm.page.ts`. Este archivo define la clase `ContactFormPage`, que representa el componente de formulario de contacto dentro de las pruebas.

La clase expone una factory llamada `create()`, que recibe las etiquetas esperadas del formulario y crea una instancia con `userEvent.setup()`. También encapsula elementos reales del formulario:

- `title`
- `nameInput`
- `lastNameInput`
- `emailInput`
- `countryCodeSelect`
- `phoneInput`
- `messageInput`
- `submitButton`
- `submittingButton`
- `successMessage`
- `errorMessage`

Además, encapsula interacciones:

- `typeName()`
- `typeLastName()`
- `typeEmail()`
- `selectCountryCode()`
- `typePhone()`
- `typeMessage()`
- `fillValidForm()`
- `submit()`

Técnicamente, `ContactFormPage` encapsula el uso de `screen` de React Testing Library y `userEvent` de `@testing-library/user-event`. Por ejemplo, los campos se localizan con consultas accesibles como `getByRole` y `getByLabelText`, mientras que las acciones del usuario se ejecutan con `user.type`, `user.selectOptions` y `user.click`.

Esto demuestra en EcoWash una transición conceptual útil:

```text
abstracción reutilizable de ContactForm
→ N pruebas particulares que consumen esa abstracción
```

> Revisión/aporte final de Kevin.

---

# Parte II — Test Driven Development (TDD)

## 1. ¿Qué es TDD?

Test Driven Development (TDD) es una metodología de desarrollo en la que las pruebas se escriben antes de implementar la funcionalidad que se quiere construir. Su idea central es usar las pruebas para guiar el desarrollo.

El proceso normalmente se representa mediante el ciclo:

```text
RED
→ GREEN
→ REFACTOR
```

En la etapa Red, primero se expresa mediante una prueba el comportamiento que esperamos. Esa prueba falla porque la solución todavía no existe o todavía no satisface ese comportamiento. Red no consiste en crear errores artificialmente, sino en convertir una expectativa en una condición verificable antes de implementar la solución.

En la etapa Green, se implementa el código mínimo necesario para lograr que la prueba pase. El objetivo es obtener el comportamiento esperado de la forma más directa posible.

En la etapa Refactor, se mejora el cómo está construida la solución sin modificar el qué ya conseguido. Es decir, se puede simplificar código, reducir duplicación o separar responsabilidades, pero el comportamiento protegido por las pruebas debe mantenerse.

## 2. Ventajas de TDD

TDD obliga a pensar primero en el comportamiento esperado antes de concentrarse en la implementación. Esto ayuda a reducir ambigüedades y permite que el desarrollo avance desde objetivos verificables.

Entre sus ventajas principales se encuentran:

- Claridad sobre el comportamiento esperado.
- Detección temprana de defectos.
- Código más modular y con responsabilidades más claras.
- Menor riesgo de regresión.
- Mayor facilidad para refactorizar.
- Más confianza al modificar funcionalidades existentes.
- Mejor mantenibilidad del software.
- Pruebas automatizadas como parte natural del proceso de desarrollo.

## 3. Limitaciones de TDD

TDD no es una solución automática para todos los problemas de software. Requiere disciplina, práctica e inversión inicial, porque antes de implementar una funcionalidad se deben definir escenarios de prueba relevantes.

Una prueba puede estar técnicamente correcta y aun así validar un comportamiento incorrecto si el requerimiento fue entendido mal. Por eso, TDD no reemplaza el análisis de requisitos ni la revisión humana.

También puede ser difícil de aplicar en integraciones externas complejas, interfaces visuales muy cambiantes o etapas exploratorias donde todavía no se sabe cuál será la solución final. Además, TDD no sustituye otros niveles de testing, como pruebas de integración, pruebas end-to-end, pruebas de interfaz o validaciones manuales cuando son necesarias.

## 4. TDD vs escribir pruebas después

La diferencia principal está en el momento en que se escriben las pruebas y en el papel que cumplen durante el desarrollo.

En TDD, el flujo esperado es:

```text
Requerimiento
→ Test
→ RED
→ Implementación
→ GREEN
→ REFACTOR
```

Cuando las pruebas se escriben después, el flujo normalmente es:

```text
Requerimiento
→ Implementación
→ Tests
→ Validación
```

Ambas estrategias pueden producir pruebas útiles. Sin embargo, solo la primera demuestra TDD si realmente ocurrió en ese orden. Encontrar tests automatizados en un proyecto no significa automáticamente que el proyecto haya sido desarrollado con TDD.

## 5. ¿Cómo contribuye TDD a la calidad?

TDD contribuye a la calidad porque introduce ciclos cortos de validación. En vez de construir una funcionalidad grande y comprobarla al final, el equipo avanza mediante comportamientos pequeños y verificables.

También favorece la sostenibilidad y la mantenibilidad. Un código diseñado para ser probado suele tener responsabilidades más claras y menor acoplamiento. Durante un refactor, las pruebas ayudan a comprobar que el comportamiento esperado se mantiene aunque cambie la estructura interna.

En resumen, TDD puede ayudar a detectar defectos temprano, reducir regresiones, facilitar refactorizaciones, documentar comportamientos importantes y aumentar la confianza del equipo al realizar cambios.

## TDD contextualizado en EcoWash

EcoWash actualmente tiene pruebas automatizadas. Sin embargo, el historial revisado no ofrece evidencia suficiente para afirmar que esas pruebas hayan sido desarrolladas históricamente mediante TDD.

La evidencia disponible muestra que `ContactForm` y `useContactForm` ya existían antes. Posteriormente, el commit EC-40 `c480f716ff4d724fed002f1f0a44b4fce046dda5` agregó:

- `ContactForm.page.ts`
- `ContactForm.test.tsx`
- `useContactForm.test.ts`
- `vitest.config.ts`
- `setupTests.ts`
- estrategia de testing/POM mediante el skill `unit-testing-standards`

Por tanto, no existe evidencia suficiente para afirmar que EC-40 utilizó históricamente TDD. La conclusión correcta es que EcoWash incorporó pruebas automatizadas y una estrategia POM, pero eso no equivale automáticamente a TDD.

Tener tests automatizados no significa automáticamente haber desarrollado mediante TDD. Aun así, TDD sí podría utilizarse como estrategia para futuros desarrollos de EcoWash, especialmente cuando se creen funcionalidades nuevas con requisitos claros.

---

# Parte III — Análisis del proyecto actual EcoWash

## 1. Pruebas identificadas

### ContactForm.test.tsx

`ContactForm.test.tsx` contiene pruebas de componente para el formulario de contacto. Renderiza el componente `ContactForm`, utiliza mocks para componentes compartidos y reemplaza `fetch` con un mock para evitar llamadas reales a servicios externos.

Los tests reales identificados son:

- Renderiza los campos del formulario y el botón de envío.
- No envía el formulario cuando los campos requeridos están vacíos.
- Envía datos válidos a `API.ROUTES.SEND`.
- Muestra mensaje de éxito y reinicia el formulario después de un envío exitoso.
- Muestra mensaje de error cuando la respuesta de la API no es correcta.

Estas pruebas validan comportamiento observable del componente desde la perspectiva de la interfaz.

### useContactForm.test.ts

`useContactForm.test.ts` prueba la lógica del hook `useContactForm`. Utiliza `renderHook`, `act` y eventos simulados para validar el estado y los handlers expuestos por el hook.

Los comportamientos cubiertos incluyen:

- Actualización de `formData` cuando se llama `handleChange`.
- Generación de errores cuando faltan campos requeridos.
- Prevención del envío cuando los datos son inválidos.
- Llamada a `fetch` con el payload esperado cuando el formulario es válido.
- Reinicio de `formData` y estado `STATUS.SUCCESS` cuando la respuesta es exitosa.
- Estado `STATUS.ERROR` cuando la respuesta de la API no es correcta.

Esta prueba corresponde a testing de lógica/hook, no a testing de interfaz completa.

## 2. Implementación del POM

El archivo `ContactForm.page.ts` implementa el Page Object de EcoWash para las pruebas del formulario de contacto.

Su estructura principal es:

- Tipos `ContactFormPageLabels` y `ContactFormPageValues`.
- Clase `ContactFormPage`.
- Constructor privado.
- Factory estática `create()`.
- Getters para localizar elementos.
- Métodos para encapsular interacciones.
- Helper privado `requiredLabelPattern()`.

Los elementos encapsulados incluyen los inputs, el select de código de país, el botón de envío y los mensajes de éxito/error. Las interacciones encapsuladas incluyen escribir texto, seleccionar un código de país, llenar el formulario completo y enviar.

El Page Object usa `screen` para localizar elementos y `userEvent` para representar interacciones del usuario. Esto permite que el archivo de test no tenga que repetir detalles como `screen.getByLabelText(...)`, `screen.getByRole(...)`, `user.type(...)` o `user.click(...)`.

## 3. Cómo las pruebas utilizan el Page Object

En `ContactForm.test.tsx`, el componente se renderiza y luego se devuelve una instancia del Page Object:

```tsx
const renderContactForm = (): ContactFormPage => {
  render(<ContactForm {...contactFormProps} />);

  return ContactFormPage.create(pageLabels);
};
```

Luego las pruebas consumen esa abstracción:

```tsx
const page = renderContactForm();

await page.fillValidForm(validFormValues);
await page.submit();

expect(page.successMessage).toBeVisible();
```

El test expresa intención: llenar un formulario válido, enviarlo y verificar el resultado. Los detalles de interacción quedan dentro de `ContactFormPage`.

## 4. Caso sin POM

Ejemplo académico; esta versión no corresponde a una versión histórica encontrada en Git.

Una prueba equivalente sin POM tendría que interactuar directamente con React Testing Library y `userEvent` dentro del archivo de test:

```tsx
it("shows success message and resets the form after successful submit", async () => {
  render(<ContactForm {...contactFormProps} />);
  const user = userEvent.setup();

  await user.type(
    screen.getByLabelText(/^Name\s*\*$/),
    validFormValues.name
  );
  await user.type(
    screen.getByLabelText(/^Last name\s*\*$/),
    validFormValues.lastName
  );
  await user.type(
    screen.getByLabelText(/^Email\s*\*$/),
    validFormValues.email
  );
  await user.selectOptions(
    screen.getByLabelText(/^Country code\s*\*$/),
    validFormValues.countryCode
  );
  await user.type(
    screen.getByLabelText(/^Phone\s*\*$/),
    validFormValues.phone
  );
  await user.type(
    screen.getByLabelText(/^Message\s*\*$/),
    validFormValues.message
  );
  await user.click(
    screen.getByRole("button", { name: ARIA_LABEL.SEND_MESSAGE })
  );

  await waitFor(() => {
    expect(screen.getByText("Message sent")).toBeVisible();
  });
});
```

Este ejemplo muestra el problema que POM intenta resolver: el test contiene muchos detalles de localización e interacción que podrían repetirse en varios casos.

## 5. Comparación SIN POM vs CON POM

| Aspecto | Sin POM | Con POM |
|---|---|---|
| Selectores | Dentro de cada test | Centralizados |
| Interacciones | Repetidas | Encapsuladas |
| Legibilidad | Más detalles técnicos | Mayor intención |
| Reutilización | Menor | Mayor |
| Mantenimiento | Cambios distribuidos | Cambios centralizados |
| Acoplamiento UI | Mayor | Menor |

Técnicamente, la versión sin POM funciona, pero cada prueba queda más expuesta a los detalles de la interfaz. Si cambia una etiqueta o la forma de localizar un campo, puede ser necesario actualizar muchas pruebas.

La versión con POM centraliza esos detalles en `ContactFormPage`. Esto permite que las pruebas se mantengan enfocadas en el comportamiento esperado y que los cambios de interacción se administren en un solo lugar.

## 6. ¿Por qué useContactForm.test.ts no necesita POM?

`useContactForm.test.ts` no necesita POM porque no prueba una página ni un componente renderizado desde la perspectiva del usuario. Utiliza `renderHook` para ejecutar el hook directamente y valida estado, handlers y efectos observables.

Aplicar POM en este caso sería innecesario porque no hay elementos visuales que localizar ni interacciones de interfaz que encapsular. Mantener la prueba como test de hook evita sobreingeniería y conserva la prueba enfocada en la lógica.

---

# Parte IV — Reflexión

## 1. ¿Qué aprendimos sobre POM?

Aprendimos que Page Object Model no es simplemente crear una clase. Su valor está en abstraer la interacción con una página o componente para que esa interacción pueda reutilizarse en múltiples pruebas.

POM se relaciona con ideas de POO como abstracción, encapsulación y responsabilidad, pero no debe confundirse con POO como concepto general. En este trabajo, POM se entiende como una forma concreta de organizar pruebas de interfaz.

También aprendimos que POM permite pasar de lo general a lo particular. Primero se define un modelo reutilizable del componente, como `ContactFormPage`, y luego cada prueba usa ese modelo para validar un caso específico. Esto mejora la legibilidad y facilita el mantenimiento cuando la interfaz cambia.

> Kevin: revisar/complementar esta reflexión con su aprendizaje personal.

## 2. ¿Qué aprendimos sobre TDD?

Al estudiar TDD entendimos que este tipo de metodología está muy orientada a la sostenibilidad y mantenibilidad del software. No se trata solamente de crear pruebas para comprobar si algo funciona, sino de establecer un proceso que permita desarrollar, validar y mejorar continuamente una solución.

El ciclo Red-Green-Refactor muestra esta idea. La etapa Red no significa provocar errores intencionalmente. Primero se aclara qué se quiere conseguir y cuáles condiciones deberían producir ese resultado. Ese comportamiento esperado se escribe como una prueba y, como la solución todavía no ha sido implementada, la prueba queda naturalmente en estado rojo.

Después viene Green, donde se implementa el código necesario para conseguir el comportamiento esperado. En este punto la prueba permite comprobar de manera concreta que la implementación realmente produce el resultado definido.

Finalmente aparece Refactor, que entra directamente en el cómo está construida la solución. Si el comportamiento ya funciona, se puede mejorar la estructura, simplificar código, reducir duplicaciones o separar mejor las responsabilidades sin cambiar el resultado esperado. Las pruebas permiten comprobar que esas mejoras no hayan roto lo que ya funcionaba.

Por eso, TDD puede verse como un proceso cíclico:

```text
definir el comportamiento
→ comprobar que falta
→ implementar
→ validar
→ mejorar
→ volver a validar
```

Este método ayuda a darle rumbo y enfoque al desarrollo, porque permite avanzar desde comportamientos definidos hacia implementaciones concretas y verificables.

## 3. ¿Los agentes y skills favorecen la mantenibilidad?

El skill real `.agents/skills/unit-testing-standards/SKILL.md` favorece la mantenibilidad porque define reglas comunes para que distintos agentes trabajen con criterios consistentes.

Entre las reglas verificadas en el archivo se encuentran:

- Usar Vitest como runner.
- Usar React Testing Library para renderizado.
- Usar `@testing-library/user-event` para interacciones.
- Usar `jsdom` como entorno de pruebas.
- Ubicar las pruebas dentro de `app/components/<feature>/tests/`.
- Usar Page Object Model en pruebas de UI/componentes.
- Mantener los locators e interacciones dentro del Page Object.
- No colocar `expect(...)` dentro del Page Object.
- Usar queries accesibles como `getByRole`, `getByLabelText` y `getByText`.
- Mockear I/O externo en el límite.
- Usar pruebas de hook/ViewModel para lógica que no requiere UI.

Estas reglas ayudan a que varios agentes o desarrolladores mantengan una estructura consistente. Sin embargo, también se necesita pensamiento crítico: un agente puede generar tests verdes directamente, pero eso no demuestra que haya existido TDD. La validación humana sigue siendo necesaria para revisar si las pruebas representan bien el comportamiento esperado y si la evidencia histórica realmente respalda las conclusiones.

## 4. ¿Qué mejoras propondríamos?

Como propuestas del equipo, consideramos razonable:

- Utilizar TDD en funcionalidades nuevas cuando existan requisitos claros.
- Documentar evidencia Red-Green-Refactor cuando se aplique TDD.
- Mantener POM para pruebas de UI donde aporte reutilización y legibilidad.
- Evitar POM en pruebas de lógica donde no aporta valor.
- Ampliar cobertura progresivamente.
- Mantener tests pequeños, legibles y enfocados.
- Revisar cuidadosamente tests generados o asistidos por IA.
- Integrar validaciones automáticas en PR/CI si el proyecto lo permite.

Estas mejoras buscan fortalecer la mantenibilidad sin convertir las pruebas en una capa innecesariamente compleja.

---

# Parte V — Uso de Inteligencia Artificial

Se utilizó Inteligencia Artificial como apoyo para organizar ideas, revisar conceptos, analizar evidencia técnica y preparar una versión académica del documento. El uso de IA no reemplaza la revisión del equipo ni la validación manual de lo que se afirma.

## Herramientas utilizadas

- ChatGPT
- Codex

## Uso realizado

La IA se utilizó para:

- Organizar investigación.
- Revisar conceptos de POM y TDD.
- Analizar código existente de EcoWash.
- Estructurar comparaciones.
- Apoyar redacción académica.
- Revisar la implementación real del POM.
- Generar el ejemplo académico sin POM.

## Validación manual

Los estudiantes deben revisar y validar el contenido final. En esta versión se deja preparado el análisis a partir de los archivos reales revisados, incluyendo:

- Conceptos principales de POM y TDD.
- Diferencia entre POM y TDD.
- Diferencia entre POM y POO.
- Evidencia técnica del código real de EcoWash.
- Historial Git local relacionado con EC-40.
- Distinción entre tests automatizados y TDD histórico.
- Comparación académica entre una prueba sin POM y la implementación real con POM.

## Porcentaje de IA

PENDIENTE DE ACUERDO ENTRE OSCAR Y KEVIN.

---

# Parte VI — Fuentes y referencias

## Fuentes del proyecto

- `EcowashProfe/app/components/contact-form/tests/ContactForm.page.ts`
- `EcowashProfe/app/components/contact-form/tests/ContactForm.test.tsx`
- `EcowashProfe/app/components/contact-form/tests/useContactForm.test.ts`
- `EcowashProfe/vitest.config.ts`
- `EcowashProfe/setupTests.ts`
- `EcowashProfe/.agents/skills/unit-testing-standards/SKILL.md`
- Commit EC-40 `c480f716ff4d724fed002f1f0a44b4fce046dda5`
- `Curso-Software-IA/tarea-03-tests/investigacion/tdd.md`
- `Curso-Software-IA/tarea-03-tests/analisis-proyecto/REFERENCIAS_ECOWASH.md`
- `Curso-Software-IA/tarea-03-tests/prompts/USO_IA.md`
- `Curso-Software-IA/tarea-03-tests/reflexion/reflexion-tdd-oscar.md`

## Fuentes externas

PENDIENTE:
incorporar fuentes confiables consultadas sobre:

- Page Object Model
- Test Driven Development
- Red-Green-Refactor

---

# Conclusión general

Page Object Model y Test Driven Development son conceptos distintos e independientes, pero ambos pueden contribuir a la calidad del software cuando se aplican en el contexto adecuado.

POM ayuda a organizar y mantener pruebas de interfaz al centralizar selectores e interacciones en una abstracción reutilizable. TDD ayuda a utilizar pruebas como guía del proceso de desarrollo mediante ciclos cortos de validación y mejora.

EcoWash permitió comprobar una implementación real de POM en las pruebas de `ContactForm`. También permitió entender que la existencia de tests automatizados no es suficiente para afirmar que se utilizó TDD. Para sostener una afirmación de TDD sería necesaria evidencia del proceso Red-Green-Refactor, no solamente el estado final de las pruebas.
