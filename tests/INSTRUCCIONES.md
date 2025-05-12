bash
   npm install
   ```
   Esto instalará Jest, la librería que utilizaremos para ejecutar los tests.

3. **Ejecuta los Tests:**
   Una vez que las dependencias estén instaladas, puedes ejecutar los tests con el siguiente comando:
   ```bash
   npm test
   ```
   Este comando ejecutará todos los archivos de tests (`.test.js`) en tu proyecto.

**Interpretando los Resultados:**

Después de ejecutar `npm test`, verás una salida en la terminal indicando si los tests pasaron o fallaron.

*   **Tests Pasados:** Si ves mensajes como `PASS` y un resumen que indica que todos los tests han pasado, ¡felicidades! Tu código funciona correctamente según las pruebas.
    ```
    PASS  ./nombreDelArchivo.test.js
    ✓ describe blabla (X ms)

    Test Suites: 1 passed, 1 total
    Tests:       X passed, X total
    Snapshots:   0 total
    Time:        Y s
    Ran all test suites.
    ```
*   **Tests Fallados:** Si ves mensajes como `FAIL`, esto significa que uno o más tests no pasaron. La salida de la terminal te mostrará detalles sobre qué tests fallaron y la razón del fallo, lo que te ayudará a depurar tu código.
    ```
    FAIL  ./nombreDelArchivo.test.js
    ● describe blabla

      expect(received).toBe(expected) // Object.is equality

      Expected: false
      Received: true

      at Object.<anonymous> (nombreDelArchivo.test.js:X:Y)
    ...
    Test Suites: 1 failed, 1 total
    Tests:       1 failed, X passed, Y total
    Snapshots:   0 total
    Time:        Z s
    Ran all test suites.
    ```

Utiliza los resultados de los tests para guiar tu desarrollo y asegurarte de que tu código cumple con los requisitos. ¡Buena suerte!
```


   npm install
   ```
   Esto instalará Jest, la librería que utilizaremos para ejecutar los tests.

3. **Ejecuta los Tests:**
   Una vez que las dependencias estén instaladas, puedes ejecutar los tests con el siguiente comando:
   ```bash
   npm test
   ```
   Este comando ejecutará todos los archivos de tests (`.test.js`) en tu proyecto.

**Interpretando los Resultados:**

Después de ejecutar `npm test`, verás una salida en la terminal indicando si los tests pasaron o fallaron.

*   **Tests Pasados:** Si ves mensajes como `PASS` y un resumen que indica que todos los tests han pasado, ¡felicidades! Tu código funciona correctamente según las pruebas.
    ```
    PASS  ./nombreDelArchivo.test.js
    ✓ describe blabla (X ms)

    Test Suites: 1 passed, 1 total
    Tests:       X passed, X total
    Snapshots:   0 total
    Time:        Y s
    Ran all test suites.
    ```
*   **Tests Fallados:** Si ves mensajes como `FAIL`, esto significa que uno o más tests no pasaron. La salida de la terminal te mostrará detalles sobre qué tests fallaron y la razón del fallo, lo que te ayudará a depurar tu código.
    ```
    FAIL  ./nombreDelArchivo.test.js
    ● describe blabla

      expect(received).toBe(expected) // Object.is equality

      Expected: false
      Received: true

      at Object.<anonymous> (nombreDelArchivo.test.js:X:Y)
    ...
    Test Suites: 1 failed, 1 total
    Tests:       1 failed, X passed, Y total
    Snapshots:   0 total
    Time:        Z s
    Ran all test suites.
    ```

Utiliza los resultados de los tests para guiar tu desarrollo y asegurarte de que tu código cumple con los requisitos. ¡Buena suerte!
