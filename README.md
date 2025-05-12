# Lección: Arrays, Objetos, Funciones y callbacks

En esta lección cubriremos:

* Introducción a los arrays
* Buscles `for` con arrays
* Introducción a los Objetos
* Métodos
* Bucles `for…in`
* Palabra clave `this`
* Objetos en Javascript
* Callbacks
* Más métodos de Arrays

## Introducción a los arrays (matrices/arreglos)

En la lección anterior discutimos los 3 tipos de datos básicos (cadenas/strings, números y booleanos) y cómo asignar esos tipos de datos a las variables. Discutimos cómo una variable solo puede apuntar a una sola cadena, número o booleano. Sin embargo, en muchos casos queremos poder apuntar a una colección de tipos de datos. Por ejemplo, ¿qué pasaría si quisiéramos hacer un seguimiento del nombre de cada estudiante en esta clase usando una sola variable, `nombresEstudiantes`. Podemos hacer eso usando Arrays. Podemos pensar en las matrices como contenedores de almacenamiento para colecciones de datos. Construir una matriz es simple, declarar una variable y establecerla en []. Luego podemos agregar al contenedor (separadas por coma) tantas cadenas, números o booleanos como queramos y acceder a esos elementos cuando lo deseemos.

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];
```

### .length

Al igual que el tipo de dato _String_ tiene un método incorporado `.length`, también lo hace la matriz. De hecho, la matriz tiene muchos métodos incorporados útiles (los discutiremos en lecciones posteriores). Al igual que la cadena `.length` cuenta los caracteres, la matriz` .length` devolverá el número de elementos en una matriz:

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

console.log(nombresEstudiantes.length);  // 4
```

### Acceso a elementos en una matriz

Podemos acceder a un elemento de una matriza en cualquier momento, solo necesitamos llamar al elemento por su posición en la matriz. Los elementos reciben una posición numérica (índice) de acuerdo con su ubicación en la matriz, en orden. El orden numérico de una matriz SIEMPRE comienza en 0, por lo que el primer elemento está en el índice 0, el segundo en el índice 1, el tercero en el 2, y así sucesivamente (esto puede ser complicado al principio, pero solo recuerda que las matrices siempre comienzan en 0).

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];
                                0         1        2        3
```

Para acceder al elemento, escribiremos el nombre o la variable de matriz, seguidos de corchetes que contienen la asignación numérica.

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

console.log(nombresEstudiantes[1]);  // 'Antonio'
```

Para acceder dinámicamente al último elemento de la matriz, utilizaremos el método `.length`. En nuestra matriz `nombresEstudiantes`, la longitud es 4. Sabemos que el primer elemento siempre será 0, y cada elemento posterior se desplaza sobre un número. Entonces, en nuestro ejemplo, el último elemento tiene un índice de 3. Usando nuestra propiedad de longitud mostraremos cómo se hace cuando no sabemos el número de elementos en una matriz:

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', ... ,'Samuel'];

console.log(nombresEstudiantes[nombresEstudiantes.length - 1]);  // 'Samuel'
```

### Asignación

Podemos asignar y reasignar cualquier índice en la matriz usando el paréntesis/índice y un "=".

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

nombresEstudiantes[0] = 'Jorge';

console.log(nombresEstudiantes);  // ['Jorge', 'Antonio', 'Sara', 'Samuel']
```
### `.push` y `.pop`

Otros dos métodos de matriz incorporados muy útiles son `.push` y` .pop`. Estos métodos se refieren a la adición y eliminación de elementos de la matriz después de su declaración inicial.

`.push` agrega un elemento al final de la matriz, incrementando su longitud en 1. `.push` devuelve la nueva longitud.

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

nombresEstudiantes.push('Patricia');

console.log(nombresEstudiantes);  // ['Martin', 'Antonio', 'Sara', 'Samuel', 'Patricia']
```

`.pop` elimina el último elemento de la matriz, disminuyendo la longitud en 1. `.pop` devuelve el elemento "reventado" (_popped_).

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

nombresEstudiantes.pop();

console.log(nombresEstudiantes);  // ['Martin', 'Antonio', 'Sara']
```

### `.unshift` y `.shift`

`.unshift` y` .shift` son exactamente como `.push` y` .pop`, excepto que operan en el primer elemento de la matriz. `.unshift(item)` colocará un nuevo elemento en la primera posición de la matriz, y `.shift()` eliminará el primer elemento de la matriz.

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

nombresEstudiantes.unshift('Leo');

console.log(nombresEstudiantes);  // ['Leo', 'Martin', 'Antonio', 'Sara', 'Samuel']

nombresEstudiantes.shift();

console.log(nombresEstudiantes);  // ['Martin', 'Antonio', 'Sara', 'Samuel']
```

### Notas sobre las matrices

Debido a que Javascript no es un lenguaje fuertemente tipado, las matrices tampoco necesitan ser tipadas. Las matrices en Javascript pueden contener múltiples tipos de datos diferentes en la misma matriz.

## Bucles `for`

La mayoría de las veces, los bucles for se utilizan para iterar sobre todos los elementos de una matriz. Usando la técnica de acceso al índice ("index access technique") podemos acceder a cada elemento de la matriz. Para hacer esto, usamos el método `.length` como punto de parada para el ciclo.

```javascript
const nombresEstudiantes = ['Martin', 'Antonio', 'Sara', 'Samuel'];

for (let i = 0; i < nombresEstudiantes.length; i++) {
    console.log(nombresEstudiantes[i]);
}

// 'Martin'
// 'Antonio'
// 'Sara'
// 'Samuel'
```

## Objetos de argumento

Cuando pasamos argumentos a una función, están contenidos en una estructura de datos tipo matriz llamada 'argumentos'. `arguments` está disponible para nosotros en cualquier lugar dentro de la función y contiene todos los argumentos que se le pasan. Si bien es como una matriz, no tiene todas las propiedades de una matriz. Una propiedad que tiene es el método `.length`. Cuando se nos da una función con un número desconocido de argumentos, podemos usar `.length` y un bucle` for` para iterar sobre todos los argumentos:

```javascript
function sumarTodosLosNumeros() {
    let sum = 0;

    for (let i = 0; i < arguments.length; i++) {
        sum = sum + arguments[i];
    }

    return sum;
}

sumarTodosLosNumeros(2, 5, 3, 4, 7, 9, 1, 0, 7, 7, 7);  // 52
```

## Introducción a los Objetos

En la anterior lección aprendimos sobre _arrays_ o matrices. Las matrices son contenedores que sostienen colecciones de datos. En esta lección, introduciremos otro contenedor de datos, el _Objeto_. Los objetos y las matrices son similares en ciertas cosas, y muy diferentes en otras. Mientras que los array pueden contener múltiples elementos relacionados unos con otros, los objetos contienen mucha información sobre una sola cosa. Los objetos se instancian usando llaves (`{}`).

```javascript
const nuevoObjeto = {};
```

### Pares Clave:Valor (`Key:Value`)

A diferencia de las matrices que tienen elementos valorados en índices, los objetos usan un concepto llamado pares de clave:valor. La clave (_key_) es el identificador y el valor (_value_) es el valor que queremos guardar en esa clave. La sintaxis es "clave: valor". Los objetos pueden contener muchos pares de clave-valor, deben estar separados por una coma (importante: sin punto y coma dentro de un objeto). Las claves son únicas en un objeto, solo puede haber una clave de ese nombre, aunque, varias claves pueden tener el mismo valor. Los valores pueden ser cualquier tipo de dato de Javascript; cadena, número, booleano, matriz, función o incluso otro objeto. En esta demostración crearemos un objeto `usuario`.

```javascript
const usuario = {
    username: 'juan.perez',
    password: 'loremipsumpwd123',
    lovesJavascript: true,
    favoriteNumber: 42
};
```

### Acceder a los valores

Una vez que tengamos los pares clave-valor, podemos acceder a esos valores llamando al nombre del objeto y la clave. Hay dos formas diferentes de hacer esto, usando puntos o usando corchetes.

Con la notación de puntos podemos llamar al nombre del objeto, un punto y el nombre de la clave. Así como llamamos a la propiedad `.length` en una matriz. La propiedad de longitud es un par de clave-valor.

```javascript
user.lovesJavascript; // true
user.username;        // juan.perez
```

La notación de corchetes es como llamar a un elemento en una matriz, aunque con corchetes debemos usar una cadena o número, o una variable que apunte a una cadena o número. Se puede llamar a cada clave envolviéndola con comillas:

```javascript
const passString = 'password';
user['lovesJavascript']; // true
user['username'];        // juan.perez
user[passString];        // loremipsumpwd123
```

Generalmente, verás que los corchetes casi siempre se usan con variables.

### Asignación de valores

Asignar valores funciona igual que acceder a ellos. Podemos asignarlos, cuando creamos el objeto, con notación de puntos o con notación de corchetes:

```javascript
const nuevoUsuario = {
    esNuevo: true
}

const loveJSString = 'lovesJavascript';

nuevoUsuario.username = 'otro.nombre.de.usuario';
nuevoUsuario['password'] = '12345';
nuevoUsuario[loveJSString] = true;
```

## Eliminando propiedades

Si queremos eliminar una propiedad, podemos hacerlo usando la palabra clave `delete`:

```javascript
const nuevoObjeto = {
    eliminarEstaPropiedad: true
};

delete nuevoObjeto.eliminarEstaPropiedad;
```

Es raro que veamos el uso de la palabra clave `delete`, muchos consideran que la mejor práctica es establecer el valor de una palabra clave en` undefined`. Dependerá de ti cuando llegue el momento.

## Métodos

En los objetos, los valores se pueden establecer en funciones. Las funciones guardadas en un objeto se denominan métodos. Hemos utilizado muchos métodos hasta ahora a lo largo de este curso. `.length`,` .push`, `.pop`, etc., son todos métodos. Podemos establecer una clave para un nombre y el valor para una función. Al igual que otras veces que llamamos métodos, llamaremos a este método usando notación de puntos y paréntesis finales (Nota: podemos llamar a un método con argumentos como lo haríamos con una función normal):

```javascript
const nuevoObjeto = {
    decirHola: function() {
        console.log('Hola a todo el mundo!');
    }
}

nuevoObjeto.decirHola(); //Hola a todo el mundo!
```

## Bucles `for…in`

A veces queremos iterar sobre cada par clave-valor en nuestro objeto. Con las matrices, utilizamos un estándar para el bucle y una variable de número de índice. Los objetos no contienen índices numéricos, por lo que el bucle estándar no funcionará para los objetos. Javascript tiene un segundo tipo de bucle for integrado llamado "_for ... in loop_". Es una sintaxis ligeramente diferente, comienza igual pero entre paréntesis declararemos una variable, la palabra clave `in` y el nombre del objeto. Esto recorrerá cada clave del objeto y finalizará cuando se hayan iterado todas las claves. Podemos usar esta clave, y la notación de corchetes, en nuestro bucle for para acceder al valor asociado con esa clave.

```javascript
const usuario = {
    username: 'juan.perez',
    password: 'loremipsumpwd123',
    lovesJavascript: true,
    favoriteNumber: 42
};

for (let clave in usuario){
    console.log(clave);
    console.log(usuario[clave]);
}

// username
// 'juan.perez'
// password
// 'loremipsumpwd123'
// lovesJavascript
// true
// favoriteNumber
// 42
```
## La palabra clave 'this'

Los objetos tienen una palabra clave autorreferencial que se puede aplicar en cada objeto llamado `this`. Cuando se llama dentro de un objeto, se refiere a ese mismo objeto. `this` puede usarse para acceder a otras claves en el mismo objeto, y es especialmente útil en métodos:

```javascript
const usuario = {
    username: 'juan.perez',
    password: 'loremipsumpwd123',
    lovesJavascript: true,
    favoriteNumber: 42,
    decirHola: function(){
        console.log( this.username + ' manda saludos!');
    }
};

usuario.decirHola(); // 'juan.perez manda saludos!'
```

Nota: la palabra clave `this` a veces puede ser uno de los temas más difíciles en Javascript. Lo estamos usando muy básicamente aquí, pero el tema se vuelve mucho más complejo muy pronto.

## Objetos en Javascript

En esta lección aprendimos qué son los Objetos y las muchas formas que existen para acceder a los valores, llamar a los métodos y asignar valores. Muchas de estas técnicas parecían muy familiares, como si las hubiéramos usado en prácticamente todos los aspectos de nuestros aprendizajes hasta ahora. Aquí hay un patrón, eso es porque TODO en Javascript es un Objeto. Las matrices son solo objetos con teclas numéricas, las cadenas son objetos bajo el capó con métodos incorporados, las funciones son en realidad objetos con sus propias propiedades especiales, todo el tiempo de ejecución de Javascript es un objeto (`window` en un navegador o` global` en el Node.js). Cuanto más trabajes con Javascript, más comenzará a tener sentido para ti. Solo recuerda, todo es un objeto.

## Callbacks

Un concepto muy importante en Javascript es la capacidad de pasar una función como argumento a otra función. Estas funciones se denominan `callbacks`. Estas funciones pueden llamarse en cualquier momento y pasar argumentos dentro de la función. Pronto descubriremos por qué las devoluciones de llamada son tan importantes para Javascript. La convención es usar `cb` como argumento para la variable que se usará de callback.

```javascript
function decirHolaAlUsuario(usuario) {
    return 'Hola ' + usuario + '!';
}

function decirAdiosAlUsuario(usuario) {
    return 'Adiós ' + usuario + '!';
}

function crearSaludo(usuario, cb) {
    return cb(usuario);
}

crearSaludo('Dan', decirHolaAlUsuario); // 'Hello Dan!'
crearSaludo('Dan', decirAdiosAlUsuario); // 'Goodbye Dan!'
```

## Más métodos de Arrays

Ya conocemos y utilizamos métodos de matriz, `.push`,` .pop`, `.shift`,` .unshift` y `.length`. Pero hay muchos más métodos disponibles de forma nativa en un array. Los métodos de los que vamos a hablar aquí se denominan "métodos de orden superior", porque toman los callbacks como argumentos.

### `.forEach`

`.forEach` es un bucle for integrado en cada array. `.forEach` toma un callback como su único argumento, e itera sobre cada elemento de la matriz y llama al callback en él. El callback puede tomar dos argumentos, el primero es el elemento en sí, el segundo es el índice del elemento (este argumento es opcional).

```javascript
const autos = ['Ford', 'Chevrolet', 'Toyota', 'Tesla'];

// Podemos escribir el callback en los paréntesis como una función anónima
autos.forEach(function(elemento, indice) {
    console.log(elemento);
});

// O podemos crear una instancia de una función para usarla como callback.
// Además, no necesitamos usar el argumento de índice, si no lo necesitas, no dudes en omitirlo.
function mostrarNombres(elemento) {
    console.log(elemento);
}

// And call that function in the forEach parentheses
autos.forEach(mostrarNombres);
```

### `.reduce`

`.reduce` ejecutará un bucle en nuestra matriz con la intención de reducir cada elemento en un elemento que se devuelve. Como es el primer argumento, acepta un callback que toma dos argumentos, primero un 'acumulador' (el resultado del método de reducción hasta ahora), y el segundo es el elemento en el que se encuentra actualmente. El callback debe contener siempre una declaración de devolución ("return"). `.reduce` también toma un segundo argumento opcional, que sería el acumulador de arranque ("starting accumulator"). Si no se suministra el acumulador de arranque, la reducción comenzará en el primer elemento de la matriz. `.reduce` siempre devolverá el acumulador cuando termine de recorrer los elementos.

```javascript
const numeros = [ 1, 2, 3, 4, 5, 6, 7, 8, 9];
const palabras = [ 'Hola,', 'mi', 'nombre', 'es', 'Martin'];

// Podemos escribir la función anónima directamente en los paréntesis de .reduce
// Si omitimos el elemento inicial, siempre comenzará en el primer elemento.
const suma = numeros.reduce(function(acc, elemento){
    return acc + elemento;
});

// Podemos escribir una función fuera de los parents de .reduce (para usar varias veces más tarde)
function multiplicarDosNumeros(a, b) {
    return a * b;
}

const productos = numeros.reduce(multiplicarDosNumeros);

// .reduce funciona en cualquier tipo de datos.
// En este ejemplo configuramos un acumulador de arranque
const frases = palabras.reduce(function(acc, elemento) {
    return acc + ' ' + elemento;
}, 'Frase completa:');

console.log(suma); // 45
console.log(productos); // 362880
console.log(frases); // "Frase completa: Hola, mi nombre es Martin"
```
### `.map`

`.map` se usa cuando queremos cambiar cada elemento de una matriz de la misma manera. `.map` toma una devolución de llamada como único argumento. Al igual que el método `.forEach`, el callback tiene el elemento y el índice de argumentos opcionales. A diferencia de `.reduce`,` .map` devolverá toda la matriz.

```javascript
const numeros = [2, 3, 4, 5];

function multiplicarPorTres(elemento) {
    return elemento * 3;
}

const doble = numeros.map(function(elemento) {
    return elemento * 2;
});

const triple = numeros.map(multiplicarPorTres)

console.log(doble); // [ 4, 6, 8, 10 ]
console.log(triple); // [ 6, 9, 12, 15 ]
```

## Abre la carpeta "homework" y completa la tarea descrita en el archivo README

## Recursos adicionales

* [Understanding Callback Functions and How to Use Them](http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/)
* [Eloquent Javascript: Higher Order Functions](https://eloquentjavascript.net/05_higher_order.html)
* [MDN: Callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)
* [MDN: Array methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
* [MDN: Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
* [MDN: this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
* [MDN: for...in Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
* [MDN: Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
* [MDN: for Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
