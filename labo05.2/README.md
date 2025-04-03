# Parte 1: Programación orientada a objetos en JavaScript

## 🧪 Laboratorio: Clases y Objetos en JavaScript

En este laboratorio aprenderás a trabajar con objetos y clases en JavaScript a través de ejemplos sencillos relacionados con libros de programación.

### 📌 Objetivo

- Comprender cómo se crean objetos literales.
- Aprender a definir clases y crear instancias (objetos).
- Acceder a propiedades y métodos.
- Usar el constructor para inicializar objetos.


### 🧱 1. Crear un objeto literal

En JavaScript, un objeto literal se define usando llaves `{}`. Vamos a definir un libro de programación como objeto:

```js
const libro = {
  titulo: "Eloquent JavaScript",
  autor: "Marijn Haverbeke",
  paginas: 472
};

console.log(libro);
```

📋 **Ejercicio**: Cambia el título y el autor por otro libro que conozcas. Imprime el objeto de nuevo.


### 🏗️ 2. Crear una clase y un objeto

En ES6 (ECMAScript 2015) se introdujo la sintaxis `class` para definir clases. Vamos a definir una clase `Libro`.

```js
class Libro {
  titulo;
  autor;
  paginas;
}
```

Una vez definida la clase, puedes crear un objeto así:

```js
const miLibro = new Libro();
console.log(miLibro);
```

📋 **Ejercicio**: ¿Qué ves por consola? ¿Qué valores tienen las propiedades?


### 🧭 3. Acceder a propiedades y métodos

Puedes asignar valores a las propiedades y definir métodos dentro de la clase. Vamos a añadir un método que describa el libro.

```js
class Libro {
  titulo;
  autor;
  paginas;

  describir() {
    return `${this.titulo}, escrito por ${this.autor}, tiene ${this.paginas} páginas.`;
  }
}

const otroLibro = new Libro();
otroLibro.titulo = "JavaScript: The Good Parts";
otroLibro.autor = "Douglas Crockford";
otroLibro.paginas = 176;

console.log(otroLibro.describir());
```

📋 **Ejercicio**: Crea otro libro diferente y llama al método `describir()`.


### 🛠️ 4. Usar el constructor

El constructor permite inicializar los atributos de un objeto en el momento de su creación:

```js
class Libro {
  constructor(titulo, autor, paginas) {
    this.titulo = titulo;
    this.autor = autor;
    this.paginas = paginas;
  }

  describir() {
    return `${this.titulo}, escrito por ${this.autor}, tiene ${this.paginas} páginas.`;
  }
}

const libroTop = new Libro("You Don't Know JS", "Kyle Simpson", 278);
console.log(libroTop.describir());
```

📋 **Ejercicio**: Crea una función que reciba un array de objetos `Libro` y muestre sus descripciones por consola.


### 🔍 5. Recorrer propiedades sin saber cuáles son

A veces queremos recorrer todas las propiedades de un objeto sin conocer sus nombres de antemano. Esto es útil, por ejemplo, para mostrar toda la información de un libro automáticamente.

Podemos hacerlo con un bucle `for...in`:

```js
const libro = {
  titulo: "Clean Code",
  autor: "Robert C. Martin",
  paginas: 464
};

for (const propiedad in libro) {
  console.log(`${propiedad}: ${libro[propiedad]}`);
}
```

📋 **Ejercicio**: Prueba a añadir una nueva propiedad (por ejemplo, `editorial`) al objeto y vuelve a ejecutar el bucle. ¿Aparece en la salida?


# Parte 2: ⏱️ Ejercicios JavaScript Asíncronos

## ✨ Objetivos del laboratorio

En este laboratorio nos adentraremos en la programación asíncrona con JavaScript, explorando tres enfoques esenciales: *callbacks*, *promesas* y *async/await*. Estas técnicas permiten gestionar operaciones que toman tiempo, como las peticiones a servidores o el uso de temporizadores, sin bloquear la ejecución del resto del código. Dominar estos métodos nos ayudará a desarrollar aplicaciones más eficientes y reactivas.

## Prueba del código

Puedes probar el código de este laboratorio en herramientas en línea como [JS Bin](https://jsbin.com) o [CodePen](https://codepen.io). Solo tienes que copiar y pegar el código en el editor y observar el resultado en la consola.

Otra opción es usar un editor de texto como Visual Studio Code (VSCode) para escribir y ejecutar el código directamente en tu entorno de desarrollo.

## 🕑 Ejercicio 1: Ejecución retardada de una función en JavaScript

### Objetivo

Crear una función en JavaScript que reciba otra función como argumento y la ejecute tras un retraso de 2 segundos.  
Este ejercicio se abordará utilizando los tres enfoques mencionados: *callbacks*, *promesas* y *async/await*.

### Entrada esperada

- Una función de *callback* que será ejecutada tras el retraso.

### Salida esperada

- La ejecución de la función de *callback* después de 2 segundos.

### Enfoque 1: Callbacks

#### 📜 Descripción del ejercicio

En este primer enfoque, implementarás una función llamada `invocarDespuesDeRetraso`, que aceptará una función de *callback* y la ejecutará tras un retraso de 2 segundos (2000 milisegundos).  
Para probarla, puedes definir una función sencilla que muestre un mensaje en la consola y pasarla como argumento a `invocarDespuesDeRetraso`.

#### Código de ejemplo

```javascript
function invocarDespuesDeRetraso(callback) {
  setTimeout(callback, 2000); // 2000 milisegundos = 2 segundos
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

invocarDespuesDeRetraso(mostrarMensaje); // Invoca la función mostrarMensaje tras 2 segundos de espera
```

#### Explicación paso a paso

1. **Definición de `invocarDespuesDeRetraso`**: Esta función recibe otra función como parámetro (*callback*) y utiliza `setTimeout` para ejecutarla tras 2000 milisegundos (2 segundos).

2. **Definición de `mostrarMensaje`**: Se trata de una función que simplemente imprime '¡Qué pasa, majo!' en la consola.

3. **Invocación de `invocarDespuesDeRetraso`**: Se llama a `invocarDespuesDeRetraso` pasando `mostrarMensaje` como argumento. Como resultado, el mensaje aparecerá en la consola después de un retraso de 2 segundos.


### Enfoque 2: Promesas

#### 📜 Descripción del ejercicio

En este enfoque, implementarás la misma lógica de retraso utilizando **promesas**. Crearás una función llamada `invocarDespuesDeRetrasoPromesa` que devuelva una promesa y ejecute la función pasada como argumento después de un retraso de 2 segundos.

#### Código de ejemplo

```javascript
function invocarDespuesDeRetrasoPromesa(callback) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
    }, 2000);
  }).then(callback);
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

invocarDespuesDeRetrasoPromesa(mostrarMensaje); // Ejecuta mostrarMensaje después de 2 segundos usando promesas
```

#### Explicación paso a paso

1. **Definición de `invocarDespuesDeRetrasoPromesa`**: Esta función devuelve una promesa que se resuelve tras un retraso de 2 segundos utilizando `setTimeout`.

2. **Uso del método `then`**: Una vez que la promesa se resuelve, se ejecuta la función `callback` pasada como argumento.

3. **Invocación de la función**: Al llamar a `invocarDespuesDeRetrasoPromesa` y pasarle `mostrarMensaje`, esta función se ejecuta tras un retraso de 2 segundos, aprovechando la sintaxis de las promesas.

---

### Enfoque 3: Async/Await

#### 📜 Descripción del ejercicio

Por último, resolverás el mismo problema usando la sintaxis moderna de **async/await**, que facilita la lectura del código asíncrono.  
Definirás una función `invocarDespuesDeRetrasoAsync` que utilice `await` para esperar 2 segundos antes de ejecutar la función de *callback*.

#### Código de ejemplo

```javascript
function esperar(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function invocarDespuesDeRetrasoAsync(callback) {
  await esperar(2000);
  callback();
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

invocarDespuesDeRetrasoAsync(mostrarMensaje); // Ejecuta mostrarMensaje tras 2 segundos usando async/await
```

#### Explicación paso a paso

1. **Definición de `esperar`**: Esta función devuelve una promesa que se resuelve tras un número determinado de milisegundos, simulando un retardo.

2. **Definición de `invocarDespuesDeRetrasoAsync`**: Se trata de una función *async* que usa `await` para pausar la ejecución durante 2 segundos antes de llamar a la función `callback`.

3. **Invocación de la función**: Al llamar a `invocarDespuesDeRetrasoAsync` con `mostrarMensaje` como argumento, el mensaje se muestra en la consola después del retraso.


### 📊 Comparativa de enfoques asíncronos en JavaScript

| Enfoque         | Sintaxis utilizada               | Ventajas principales                                     | Consideraciones                                      |
|------------------|----------------------------------|----------------------------------------------------------|------------------------------------------------------|
| **Callbacks**     | `setTimeout(callback, 2000)`     | Sencillo y directo                                       | Puede complicarse con múltiples operaciones anidadas (callback hell) |
| **Promesas**      | `new Promise(...).then(...)`     | Mejora la legibilidad y manejo de errores                | Requiere entender la API de promesas                |
| **Async/Await**   | `async` / `await` con promesas   | Sintaxis clara y parecida al código síncrono             | Necesita funciones marcadas como `async`            |



### 🧭 ¿Cuándo usar cada enfoque?

Elegir entre *callbacks*, *promesas* o *async/await* depende del contexto, la complejidad del código y la legibilidad que busques mantener:

- **Callbacks**  
  Útiles en casos muy simples o cuando trabajas con APIs antiguas que no devuelven promesas. Son directos, pero pueden volverse difíciles de leer y mantener si hay múltiples operaciones encadenadas.

- **Promesas**  
  Recomendadas cuando necesitas encadenar varias operaciones asíncronas de forma más controlada y con mejor manejo de errores. Mejoran la estructura del código respecto a los callbacks.

- **Async/Await**  
  La opción más moderna y legible. Ideal para flujos complejos o secuenciales de código asíncrono. Facilita el uso de estructuras como `try/catch` para el manejo de errores y se asemeja mucho al estilo del código síncrono tradicional.

> En resumen: usa *callbacks* si la lógica es trivial, *promesas* si necesitas encadenar procesos, y *async/await* si quieres un código más limpio y fácil de seguir.

## 🕑 Ejercicio 2: Ejecución repetida de una función en JavaScript

### Objetivo
Implementar una función en JavaScript que reciba otra función como argumento y la ejecute repetidamente cada 1 segundo. Este ejercicio se abordará utilizando los tres enfoques mencionados: *callbacks*, *promesas* y *async/await*

### Entrada esperada

- Una función de *callback* que será ejecutada repetidamente cada 1 segundo

### Salida esperada

- La ejecución de la función de *callback* cada 1 segundo

### Enfoque 1: Callbacks

#### 📜 Descripción del ejercicio
En este primer enfoque, implementarás una función llamada `ejecutarRepetidamenteConCallback`, que aceptará una función de *callback* y la ejecutará repetidamente cada 1 segundo utilizando `setInterval`. 

En JavaScript, `setInterval()` es un método que permite ejecutar una función o fragmento de código de manera repetitiva a intervalos de tiempo constantes, especificados en milisegundos. Al invocar `setInterval()`, se establece un temporizador que, una vez transcurrido el intervalo definido, ejecuta la función indicada y continúa haciéndolo indefinidamente hasta que se detenga explícitamente mediante `clearInterval()`. Por ejemplo, si se desea que una función llamada `miFuncion` se ejecute cada segundo, se puede utilizar `setInterval(miFuncion, 1000);`. Es importante tener en cuenta que el identificador devuelto por `setInterval()` es necesario para detener la ejecución periódica utilizando `clearInterval()`.

Para detener la ejecución después de un tiempo determinado, puedes utilizar `setTimeout` para llamar a `clearInterval.

#### Código de ejemplo

```javascript
function ejecutarRepetidamenteConCallback(callback, intervalo, duracion) {
  const intervalId = setInterval(callback, intervalo);

  setTimeout(() => {
    clearInterval(intervalId);
    console.log('Ejecución detenida.');
  }, duracion);
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

const intervalo = 1000; // 1 segundo
const duracion = 5000; // 5 segundos

ejecutarRepetidamenteConCallback(mostrarMensaje, intervalo, duracion);
```


#### Explicación paso a paso

1. **Definición de `ejecutarRepetidamenteConCallback`** Esta función recibe una función de *callback*, un intervalo en milisegundos y una duración total en milisegundos. Utiliza `setInterval` para ejecutar la función de *callback* repetidamente cada `intervalo` milisegundo.

2. **Uso de `setTimeout` para detener la ejecución** Después de `duracion` milisegundos, `setTimeout` ejecuta una función que llama a `clearInterval` para detener la ejecución repetida y muestra un mensaje en la consola indicando que la ejecución ha sido detenida.

3. **Definición de `mostrarMensaje`** Una función simple que imprime '¡Qué pasa, majo!' en la consola.

4. **Invocación de `ejecutarRepetidamenteConCallback`** Se llama a `ejecutarRepetidamenteConCallback` pasando `mostrarMensaje`, el intervalo de 1 segundo y la duración total de 5 segundos como argumentos. Como resultado, '¡Qué pasa, majo!' se imprimirá en la consola cada segundo durante 5 segundos, y luego la ejecución se detendrá.

### Enfoque 2: Promesas

#### 📜 Descripción del ejercicio

En este enfoque, implementarás la misma lógica de ejecución repetida utilizando **promesas**. Crearás una función llamada `ejecutarRepetidamenteConPromesa` que devuelva una promesa y ejecute la función pasada como argumento repetidamente cada 1 segundo durante una duración total especificaa.

#### Código de ejemplo


```javascript
function ejecutarRepetidamenteConPromesa(callback, intervalo, duracion) {
  return new Promise((resolve) => {
    const intervalId = setInterval(callback, intervalo);

    setTimeout(() => {
      clearInterval(intervalId);
      console.log('Ejecución detenida.');
      resolve();
    }, duracion);
  });
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

const intervalo = 1000; // 1 segundo
const duracion = 5000; // 5 segundos

ejecutarRepetidamenteConPromesa(mostrarMensaje, intervalo, duracion)
  .then(() => console.log('Promesa resuelta.'));
```


#### Explicación paso a paso

1. **Definición de `ejecutarRepetidamenteConPromesa`**: Esta función devuelve una nueva promesa que configura `setInterval` para ejecutar la función de *callback* cada `intervalo` milisegundos.

2. **Uso de `setTimeout` para detener la ejecución y resolver la promesa**: Después de `duracion` milisegundos, `setTimeout` ejecuta una función que llama a `clearInterval` para detener la ejecución repetida, muestra un mensaje en la consola indicando que la ejecución ha sido detenida y resuelve la promea.

3. **Definición de `mostrarMensaje`**: Una función simple que imprime '¡Qué pasa, majo!' en la consola.

4. **Invocación de `ejecutarRepetidamenteConPromesa`**: Se llama a `ejecutarRepetidamenteConPromesa` pasando `mostrarMensaje`, el intervalo de 1 segundo y la duración total de 5 segundos como argumentos. Se encadena un `.then()` para imprimir 'Promesa resuelta.' una vez que la promesa se resuelve. Como resultado, '¡Qué pasa, majo!' se imprimirá en la consola cada segundo durante 5 segundos, luego la ejecución se detendrá y se imprimirá 'Promesa resuelta'.


### Enfoque 3: Async/Await

#### 📜 Descripción del ejercicio

Por último, resolverás el mismo problema usando la sintaxis moderna de **async/await**, que facilita la lectura del código asíncrono.  
Definirás una función `ejecutarRepetidamenteConAsyncAwait` que utilice `await` para esperar el intervalo especificado antes de cada ejecución de la función de *callback*, repitiendo este proceso durante la duración total especificada.

#### Código de ejemplo

```javascript
function esperar(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

async function ejecutarRepetidamenteConAsyncAwait(callback, intervalo, duracion) {
  const repeticiones = Math.floor(duracion / intervalo);
  for (let i = 0; i < repeticiones; i++) {
    callback();
    await esperar(intervalo);
  }
  console.log('Ejecución detenida.');
}

function mostrarMensaje() {
  console.log('¡Qué pasa, majo!');
}

const intervalo = 1000; // 1 segundo
const duracion = 5000; // 5 segundos

ejecutarRepetidamenteConAsyncAwait(mostrarMensaje, intervalo, duracion);

```

**Nota:** Es posible que esta solución no funcione bien en algunas aplicaciones como `jsbin` o `codepen`.


#### 🔍 Explicación paso a paso

1. **Definición de `esperar(ms)`**:  
   Esta función auxiliar devuelve una promesa que se resuelve después de `ms` milisegundos. Internamente, utiliza `setTimeout` para simular una espera.

2. **Definición de `ejecutarRepetidamenteConAsyncAwait`**:  
   Es una función declarada como `async`, lo que permite usar `await` en su interior.  
   - Guarda el tiempo de inicio con `Date.now()`.
   - Inicia un bucle `while` que se ejecuta mientras no se haya alcanzado la duración total.
   - Dentro del bucle, se ejecuta la función `callback`.
   - Luego, se espera `intervalo` milisegundos antes de repetir.

3. **Definición de `mostrarMensaje`**:  
   Una simple función que imprime `'¡Qué pasa, majo!'` en la consola.

4. **Invocación de `ejecutarRepetidamenteConAsyncAwait`**:  
   Llama a la función pasándole como argumentos la función de *callback*, el intervalo (1 segundo) y la duración total (5 segundos).  
   El resultado es que se imprime `'¡Qué pasa, majo!'` cada segundo durante 5 segundos. Una vez transcurrido ese tiempo, se imprime `'Ejecución detenida.'`.


## 📁 Ejercicio 3: Leer un fichero CSV en Node.js usando FS

### 🎯 Objetivo

Leer el contenido de un archivo CSV ubicado en disco usando el módulo `fs` de Node.js. Este ejercicio tiene como propósito que compruebes por ti mismo cómo funciona el acceso a disco en Node.js y entiendas por qué es necesario usar técnicas asincrónicas.

> ⚠️ **Advertencia importante**  
> Este ejercicio **solo funciona en JavaScript del lado del servidor usando Node.js**.  
> No puedes incrustar este código directamente en un archivo HTML o ejecutarlo en el navegador, ya que el módulo `fs` (file system) **no está disponible en entornos de cliente** por motivos de seguridad.

## 🧪 Intento 0: Lectura síncrona (incorrecta) — ¡NO FUNCIONA COMO ESPERAS!

En este primer intento, vamos a intentar leer un fichero CSV usando el módulo `fs` de forma **supuesta** "síncrona", pero sin usar `callbacks`, `promesas` ni `async/await`.

Queremos que veas **qué ocurre si intentas usar `fs.readFile` sin respetar su naturaleza asincrónica**.

➡️ [Descargar fichero CSV de prueba](./datos/datos.csv)

### 📜 Código (No es correcto)

```javascript
const fs = require('fs');

let datosCSV;

fs.readFile('datos.csv', 'utf8', (err, data) => {
  if (err) {
    console.error('Error leyendo el archivo:', err);
    return;
  }
  datosCSV = data;
});

console.log('Contenido del CSV:', datosCSV);
```

### 🔍 ¿Qué ocurre?

Este código parece que debería funcionar: primero se lee el archivo y luego se imprime el contenido. **¡Pero no es así!**  
Cuando lo ejecutes, probablemente veas:

```
Contenido del CSV: undefined
```

¿Por qué? Porque `fs.readFile` es **asíncrono**: la lectura del archivo ocurre *después* de que `console.log` se haya ejecutado.  
Este fragmento sirve como **experimento inicial** para que compruebes cómo se comporta la asincronía en Node.js.

⏯️ **¡Prueba este código tú mismo y comprueba que no funciona como esperas!**

---

## 🔁 Enfoques correctos: Callbacks, Promesas y Async/Await

Ahora que has visto que el intento anterior no funciona, vamos a abordar el problema correctamente.  
No te daremos el código completo, pero sí **las pistas necesarias** para implementar una solución que funcione.

---

### ☎️ Enfoque 1: Callbacks

#### 🧠 Pistas

- Utiliza `fs.readFile` pasando una función de *callback* como tercer argumento.
- Esa función recibirá dos parámetros: `err` y `data`.
- Dentro del callback, comprueba si hay error y si no, imprime `data`.

#### 🧩 Pseudocódigo

```
fs.readFile(ruta, codificacion, (error, datos) => {
  si hay error:
    mostrar error
  si no:
    mostrar contenido leído
});
```

---

### 💬 Enfoque 2: Promesas

#### 🧠 Pistas

- Usa `fs.promises.readFile` o convierte manualmente `fs.readFile` en una promesa.
- Una vez que tengas una promesa, puedes encadenar un `.then()` para procesar los datos.
- Maneja los errores con `.catch()`.

#### 🧩 Pseudocódigo

```
fs.promises.readFile(ruta, codificacion)
  .then((datos) => {
    mostrar contenido leído
  })
  .catch((error) => {
    mostrar error
  });
```

---

### 🧘 Enfoque 3: Async/Await

#### 🧠 Pistas

- Define una función `async` que use `await` para esperar a que termine la lectura.
- Usa `fs.promises.readFile` dentro de esa función.
- Encierra la llamada en un `try/catch` para capturar errores.

#### 🧩 Pseudocódigo

```
async function leerArchivo() {
  try {
    datos = await fs.promises.readFile(ruta, codificacion);
    mostrar contenido leído
  } catch (error) {
    mostrar error
  }
}
```

---

### ✅ Conclusión

Este ejercicio te servirá para interiorizar el comportamiento **asíncrono** de Node.js al acceder al sistema de archivos. Comprobarás por ti mismo cómo las técnicas modernas como `promesas` y `async/await` simplifican mucho la gestión de tareas retardadas.

