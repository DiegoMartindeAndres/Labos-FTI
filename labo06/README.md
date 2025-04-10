# 🧪 Laboratorio 6: DOM 🧱 y BOM 🌐


## 🧭 Introducción al laboratorio

Este laboratorio está diseñado para que explores de forma práctica cómo JavaScript puede interactuar con una página web a través del DOM (Document Object Model) y el BOM (Browser Object Model).

A lo largo de los ejercicios, trabajarás con un archivo `index.html` ya preparado, modificando únicamente el código JavaScript y añadiendo código `HTML` si fuera necesario, para observar cómo se actualizan en tiempo real los contenidos, estilos y estructuras del documento web.

➡️ [Descargar código base](code/index.html)

🌱 ¡Aprenderás haciendo! Así que no tengas miedo de equivocarte. Cada línea de código que pruebes será un paso más para convertirte en un gran aprendiz.


## Manipulación del `innerHTML` en el DOM ✨

Vamos a modificar el contenido de un elemento HTML usando `innerHTML`. 

En la página HTML proporcionada, tenemos un título:

```html
<h1 id="titulo-principal">¡Hola, mundo!</h1>
```

Podemos cambiar su contenido dinámicamente con JavaScript:

```javascript
document.getElementById("titulo-principal").innerHTML = "¡Texto cambiado con JavaScript!";
```

Este código selecciona el elemento con `id="titulo-principal"` y cambia su contenido interno.

### Prueba este código 🧪

Para abrir la **consola de desarrollador** en los navegadores más comunes, puedes usar los siguientes atajos de teclado:

### 🧑‍💻 **Atajos para abrir la consola:**

| Navegador        | Sistema Operativo | Atajo de teclado          |
|------------------|-------------------|---------------------------|
| **Google Chrome**| Windows/Linux     | `Ctrl` + `Shift` + `J`    |
|                  | macOS             | `Cmd` + `Option` + `J`    |
| **Firefox**      | Windows/Linux     | `Ctrl` + `Shift` + `K`    |
|                  | macOS             | `Cmd` + `Option` + `K`    |
| **Microsoft Edge**| Windows           | `Ctrl` + `Shift` + `J`    |
|                  | macOS             | `Cmd` + `Option` + `J`    |
| **Safari**       | macOS             | `Cmd` + `Option` + `C` *(Primero debes activar el menú de desarrollo en Preferencias > Avanzado > "Mostrar menú Desarrollo")*

---

🛠️ Alternativamente, también puedes abrir las herramientas de desarrollador (que incluyen la consola) con:

- `F12` en Windows/Linux
- `Cmd` + `Option` + `I` en macOS

Y luego ir a la pestaña **"Consola"**.

Después prueba a copiar y pegar este código.

```javascript
document.getElementById("parrafo1").innerHTML = "Este párrafo ha sido modificado con <strong>JavaScript</strong>! modificando el DOM";
```

Verás que el contenido del párrafo cambia y respeta las etiquetas HTML incluidas en el nuevo valor.

---

### 🏆 Ejercicio para practicar 

1. Crea un botón en tu HTML:
   
   ```html
   <button id="boton-cambiar">Cambiar Contenido</button>
   ```

2. Añade este script en tu archivo JavaScript o en la consola:

   ```javascript
   document.getElementById("boton-cambiar").addEventListener("click", function() {
       document.getElementById("subtitulo").innerHTML = "¡Este subtítulo ha cambiado!";
   });
   ```

3. Al hacer clic en el botón, el subtítulo cambiará automáticamente.

¡Experimenta con diferentes elementos y prueba a cambiar contenido dinámicamente! 🚀

---

## Cambiar el atributo de un elemento 🎯

Vamos a modificar los atributos de algunos elementos en nuestra página web utilizando JavaScript. Aprenderás a:

- Usar `setAttribute()` para cambiar el valor de un atributo.
- Modificar atributos específicos con `element.atributo = nuevoValor`.
- Ver los cambios en tiempo real en el navegador.

### Código de prueba 🧪


- Código para cambiar el enlace del W3C:
 

```javascript
// Cambiar el enlace del W3C
let enlace = document.getElementById("w3c-enlace");
enlace.setAttribute("href", "https://developer.mozilla.org/");
enlace.textContent = "Visita MDN en vez del W3C";
```

- Código para cambiar la imagen de ejemplo (cambiamos el tamaño de la imagen en realidad)

```javascript
// Cambiar la imagen de ejemplo
let imagen = document.getElementById("imagen-ejemplo");
imagen.src = "https://placehold.co/500x300";
imagen.alt = "Nueva imagen de ejemplo";
```

- Código para cambiar el placeholder de un campo de entrada:

```javascript
// Modificar el placeholder de un campo de entrada
let inputNombre = document.getElementById("nombre");
inputNombre.placeholder = "Escribe tu nombre completo";
```

- Código para cambiar el valor de un botón:

```javascript
// Hacer que el botón de enviar tenga otro texto
let boton = document.getElementById("boton-enviar");
boton.value = "Enviar Formulario 📩";
```

### ¿Qué ocurre? 🤔

- **El enlace cambia**: Ahora apunta a `developer.mozilla.org` en lugar de `w3.org`.
- **La imagen cambia**: Su URL se modifica, mostrando una nueva imagen.
- **El input cambia**: El texto del `placeholder` se actualiza.
- **El botón cambia**: Su valor pasa a ser "Enviar Formulario 📩".

### 🏆 Ejercicios

#### 1️⃣ Cambiar el color de fondo del formulario
Modifica el color de fondo del formulario (`formulario`) para que se vea negro `.style.backgroundColor`, color que deberías poner es "#000000".

[Puedes probar otros colores.](https://www.w3schools.com/colors/colors_picker.asp)

<details>
  <summary>¿No sabes cómo hacerlo? 🤔</summary>
<br>

¿Seguro que quieres ganar?

Aquí te dejo el código de la aplicación completa. Esto es por si te atascas.


> [!WARNING]
> Recuerda: **Nadie ganó un Roland Garros viendo jugar a Rafa Nadal por la TV.**
> **Deberías intentarlo por tu cuenta.**

<br>

<div align="center">
    <img src="img/rafa.jpg" alt="Rafa Nadal">
</div>

<br>
<br>



```javascript
let formulario = document.getElementById("formulario");
formulario.style.backgroundColor = "#000000";
```

</details>
<br>

#### 2️⃣ Agregar un `title` dinámico al título principal
Haz que el `h1` (`titulo-principal`) tenga un `title="Este es un título dinámico"`. 

Ojo! solo podrás ver el cambio si pasas el ratón por encima del título.
<details>
  <summary>Ver solución 👀</summary>
<br>

```javascript
let titulo = document.getElementById("titulo-principal");
titulo.setAttribute("title", "Este es un título dinámico");
```

¿Crees que no ha cambiado nada?, prueba a pasar el ratón por encima de "¡Hola, mundo!".

</details>
<br>

#### 3️⃣ Modificar el `target` del enlace
Cambia el atributo `target` del enlace (`w3c-enlace`) para que abra en la misma pestaña (`_self`). Para que si pulsas el enlace no se abra en una ventana nueva.

<details>
  <summary>Necesitas ayuda con esto? 💡</summary>
<br>

```javascript
let enlace = document.getElementById("w3c-enlace");
enlace.setAttribute("target", "_self");
```

</details>
<br>

## 🧪 Cambiar todos los elementos de una clase con `getElementsByClassName`

En este pequeño experimento vamos a modificar todos los elementos que tengan la clase `elemento-lista` usando JavaScript. El objetivo es que aprendáis a seleccionar múltiples nodos del DOM y trabajar con ellos en bucle.

Recuerda que `querySelectorAll` devuelve un NodeList estático, mientras que `getElementsByClassName` es una colección viva (live collection).

### 👨‍💻 Código de prueba (para que lo veas funcionar)

Pega este código en la consola de desarrollador.

```js
  let elementos = document.getElementsByClassName("elemento-lista");
  for (let i = 0; i < elementos.length; i++) {
    elementos[i].innerHTML = "Elemento modificado " + (i + 1);
  }
```

---

### 🔍 Qué hace este código

1. Busca todos los elementos con la clase `"elemento-lista"`.
2. Recorre todos esos elementos con un bucle `for`.
3. Cambia su contenido (`innerHTML`) por un texto nuevo que incluye su posición (empezando en 1).

---

### 🧠 Ejercicio propuesto

Modifica ahora el código para que en vez de usar `getElementsByClassName`, utilices `querySelectorAll`.  
Además, haz que cada elemento se muestre en **mayúsculas**.

Sugerencia: Usa `forEach` y `textContent.toUpperCase()`

#### 🧭 ¿Dónde puedo buscar información sobre `querySelectorAll`?

Buena pregunta 😄 Puedes consultar la documentación oficial en la web de MDN (Mozilla Developer Network), que es una referencia muy recomendable:

👉 [Documentación de querySelectorAll en MDN](https://developer.mozilla.org/es/docs/Web/API/Document/querySelectorAll)

> Te recomiendo visitar el enlace, leer los ejemplos que proponen y probar variaciones por tu cuenta. Cuanto más experimentes, mejor lo entenderás.

---

#### ✅ Resultado esperado:
```html
<li class="elemento-lista">ELEMENTO MODIFICADO 1</li>
<li class="elemento-lista">ELEMENTO MODIFICADO 2</li>
<li class="elemento-lista">ELEMENTO MODIFICADO 3</li>
```

Sugerencia: Cuando lo tengas funcionando, utiliza `console.log` dentro del bucle o del `forEach` para verificar que el contenido realmente ha cambiado.


<details>
  <summary>¿Necesitas ayuda?</summary>
<br>


```js
  let elementos = document.querySelectorAll(".elemento-lista");
  elementos.forEach((el, i) => {
    el.textContent = ("Elemento modificado " + (i + 1)).toUpperCase();
    console.log(el.textContent); // Mostrar en consola para comprobar
  });
```

### 🧩 ¿Qué hace este código?

- `querySelectorAll(".elemento-lista")` selecciona todos los elementos con esa clase, igual que antes, pero con un selector CSS más potente.
- Se recorre el `NodeList` con `forEach`.
- Se modifica el contenido con `textContent` (en lugar de `innerHTML`) para trabajar solo con texto plano.
- Se convierte a mayúsculas con `.toUpperCase()`.
- Finalmente, se imprime cada resultado en la consola con `console.log`.


</details>
<br>

## 🧩 Insertar un nuevo elemento en una lista desordenada

Vamos a ver cómo añadir dinámicamente un nuevo elemento `<li>` a la lista desordenada ya presente en tu HTML. Este es un ejemplo clásico de manipulación del **DOM** (Document Object Model) usando JavaScript.


### 🧪 Código de prueba

Prueba este código en la consola.

```javascript
let nuevaTarea = document.createElement("li");             // Creamos un nuevo elemento <li>
nuevaTarea.innerText = "Elemento nuevo";                   // Le damos contenido de texto
document.getElementById("lista-desordenada").appendChild(nuevaTarea);  // Lo añadimos al final de la lista
```

🔍 **Observa la consola** o simplemente mira visualmente en la página si el nuevo elemento aparece como un cuarto ítem en la lista.

---

### 🎯 Ejercicio propuesto

Ahora es tu turno. Haz un pequeño script que:

1. Cree un nuevo elemento `<li>` con el texto `"Tarea añadida por el usuario"`.
2. Lo añada a la lista desordenada cuando se pulse un botón.

Puedes seguir estos pasos:

1. Añade un botón en el HTML
2. Añade el código JS necesario en la etiquetas  `<script>` de tu HTML

<details>
  <summary>¿No sabes cómo hacerlo? 🤔</summary>
<br>

```html
<button id="boton-agregar">Agregar tarea</button>
```

```javascript
document.getElementById("boton-agregar").addEventListener("click", function() {
    let nuevaTarea = document.createElement("li");
    nuevaTarea.innerText = "Tarea añadida por el usuario";
    document.getElementById("lista-desordenada").appendChild(nuevaTarea);
});
```

</details>
<br>


### 🧠 Pista

- Asegúrate de que el código JavaScript se ejecuta **después** de que el HTML esté cargado. Puedes colocar el `<script>` al final del body, o usar `window.onload`.

## 🗑️ Eliminar un nodo existente

Vamos a trabajar con la lista ordenada (`<ol>`) que ya existe en el documento HTML. El objetivo es eliminar su **primer elemento** cada vez que se pulse un botón.

### 🔹 Código de prueba 

Añade este botón justo después de la lista ordenada y el código javascript antes del cierre de la etiqueta `</body>` en tu archivo HTML:

```html
<button id="boton-eliminar">Eliminar primer paso</button>
<script>
  let lista = document.getElementById("lista-ordenada");
  let boton = document.getElementById("boton-eliminar");

  boton.addEventListener("click", () => {
    if (lista.firstElementChild) {
      lista.removeChild(lista.firstElementChild);
      console.log("Elemento eliminado");
    } else {
      alert("No quedan elementos en la lista.");
    }
  });
</script>
```

💡 **¿Qué hace este código?**
- Obtiene la referencia al botón y a la lista ordenada.
- Al hacer clic en el botón, elimina el primer `<li>` de la lista si existe.
- Muestra un mensaje en consola cuando elimina un elemento o si ya no queda ninguno.

---

### ✏️ Ejercicio propuesto 1
Si te fijas, cuando no quedan elementos en la lista ordenada, se muestra un mensaje en la consola. Pero no ocurre ninguna otra acción.

¿Te atreves a lanzar una alerta con la información en lugar de escribirlo por consola?

### ✏️ Ejercicio propuesto 2
Vamos a mejorarlo un poco más. Si no quedan elementos, no debería poderse pulsar el botón. ¿Se te ocurre una idea para que cuando esto ocurra, el botón se desactive y no se pueda pulsar?

<details>
  <summary>¿No sabes cómo hacerlo? 🤔</summary>
<br>

Habría que cambiar este función.

```js
  boton.addEventListener("click", () => {
    if (lista.firstElementChild) {
      lista.removeChild(lista.firstElementChild);
      console.log("Elemento eliminado");

      // Comprobamos si ya no quedan elementos en la lista
      if (!lista.firstElementChild) {
        boton.disabled = true; // Deshabilitamos el botón
      }
    }
  });
```

</details>
<br>

### ✏️ Ejercicio propuesto 2

Ahora te toca a ti:

1. Crea un nuevo botón que **restaure la lista original** con los tres elementos: “Paso uno”, “Paso dos” y “Paso tres”.
2. El botón debe aparecer bajo el anterior.
3. Cuando se pulse, la lista debe volver a su estado inicial, aunque ya se hayan eliminado todos sus elementos.

Puedes usar `innerHTML` para restablecer el contenido de la lista, o crear los elementos manualmente con `createElement`.

<details>
  <summary>¿No sabes cómo hacerlo? 🤔</summary>
<br>

### ✅ Solución al ejercicio

Añade este segundo botón y el nuevo manejador de evento justo debajo del anterior:

```html
<button id="boton-restaurar">Restaurar lista</button>
<script>
  let botonRestaurar = document.getElementById("boton-restaurar");

  botonRestaurar.addEventListener("click", () => {
    lista.innerHTML = `
      <li class="paso">Paso uno</li>
      <li class="paso">Paso dos</li>
      <li class="paso">Paso tres</li>
    `;
    console.log("Lista restaurada");
  });
</script>
```

### 🔍 Qué se aprende con esto

- Uso del **DOM** para acceder y modificar nodos.
- Cómo eliminar un nodo hijo con `removeChild`.
- Cómo modificar el contenido completo de un elemento con `innerHTML`.
- Cómo controlar la interacción del usuario a través de eventos (`addEventListener`).

</details>
<br>

## 🎨 Cambiar estilos al pasar el ratón

Vamos a aprender a **modificar el estilo de un elemento del DOM** cuando el puntero del ratón pasa por encima de él (`mouseover`) y restaurarlo cuando se retira (`mouseout`). Para ello, vamos a usar el subtítulo `<h2>` que ya existe en el HTML con `id="subtitulo"`.

### 🧪 Código de prueba

Añade este bloque de JavaScript al final del `body`, o en un archivo externo que se cargue al final, para que funcione correctamente:

```javascript
let subtitulo = document.getElementById("subtitulo");

subtitulo.addEventListener("mouseover", () => {
    subtitulo.style.color = "red";
});

subtitulo.addEventListener("mouseout", () => {
    subtitulo.style.color = "black";
});
```

Con este código:

- Cuando pasas el ratón por encima del subtítulo, **el texto se pone rojo**.
- Cuando lo quitas, **vuelve al color negro**.

Puedes probarlo recargando la página y pasando el ratón sobre el subtítulo.

---

### ✍️ Ejercicio propuesto

Haz lo siguiente:

1. Elige **otro elemento de la página** (puede ser un párrafo, una imagen o un botón del formulario).
2. Añade un comportamiento similar: cambia **otro estilo CSS** (por ejemplo, `backgroundColor`, `fontSize`, `border`, etc.) al pasar el ratón y vuelve al estilo original al salir.


¿Te animas a hacer que el botón de enviar aumente su tamaño al pasar el ratón? 😏

## 🕒 Mostrar la hora actual con BOM

Vamos a trabajar con el **BOM (Browser Object Model)** para actualizar dinámicamente la hora en nuestra página web. Para ello, utilizaremos el método `setInterval()` que nos permitirá ejecutar una función cada segundo ⏱️.

### 🧪 Código de prueba

Añade este código dentro de la etiqueta `<script>` justo antes del cierre de `</body>` en el HTML. El `span` con el `id="span-ejemplo"` ya está incluido en el archivo `index.html` que tienes, por lo que solo hace falta el script:

```javascript
setInterval(() => {
  let ahora = new Date();
  document.getElementById("span-ejemplo").innerText = ahora.toLocaleTimeString();
}, 1000);
```

Este fragmento hace lo siguiente:

1. Cada 1000 milisegundos (1 segundo), ejecuta una función.
2. Crea un nuevo objeto `Date` con la hora actual.
3. Obtiene el `span` con `id="span-ejemplo"` y reemplaza su contenido con la hora actual usando `.toLocaleTimeString()` para que se muestre en formato legible.

👀 Si lo haces bien, el `span` de la frase _"Esto es un **ejemplo de uso de span** dentro de un párrafo."_ se transformará en un reloj que se actualiza en tiempo real.

---

### 💪 Ejercicio propuesto

Modifica el código anterior para que también se muestre la **fecha completa** (día, mes, año) junto a la hora, con el siguiente formato:

```
10/04/2025 14:35:08
```

💡 Pista: Puedes usar `.toLocaleDateString()` para obtener la fecha, y combinarla con `.toLocaleTimeString()` usando una plantilla de texto o concatenación.

## 🎨 Cambiar el fondo de la página con un botón

### Código de ejemplo 🧪

Vamos a añadir un botón al documento HTML para que, al hacer clic, cambie el color de fondo de toda la página. Vamos a usar `document.body.style.backgroundColor`.

📄 Inserta esto justo antes de la etiqueta `</body>` en tu HTML:

```html
<!-- Botón para cambiar el fondo -->
<button id="cambiar-fondo">Cambiar fondo</button>

<!-- Script que reacciona al botón -->
<script>
  const botonFondo = document.getElementById('cambiar-fondo');

  botonFondo.addEventListener('click', () => {
    document.body.style.backgroundColor = '#f0f8ff';
    console.log('Color de fondo cambiado a #f0f8ff');
  });
</script>
```

Este código hace lo siguiente:
- Inserta un botón con el texto “Cambiar fondo”.
- Usa JavaScript para escuchar el clic en el botón.
- Cambia el color de fondo de `document.body` cuando se hace clic.
- Muestra un mensaje en la consola para confirmar que el cambio se ha realizado.

---

### 📝 Ejercicio propuesto

🔧 **Modifica el código para que cada vez que se haga clic el fondo cambie a un color aleatorio.**

👉 Pistas:
- Crea una función que genere un color hexadecimal aleatorio.
- Llama a esa función dentro del `addEventListener` para cambiar el color.

¡Cuando lo tengas, prueba a hacer clic varias veces y observa cómo cambia el fondo! 🎉

<details>
  <summary>¿No sabes cómo hacerlo? 🤔</summary>
<br>


</details>
<br>

## 🖼️ Redimensionar la imagen con botones + y -

Vamos a añadir dos botones que permitan **aumentar** y **reducir** el tamaño de la imagen existente en la página. La manipulación se hará mediante JavaScript, accediendo al DOM con `getElementById` y modificando los atributos `style.width` y `style.height`.


### ✨ Código de ejemplo para probar

Primero deberemos crear dos botones debajo de la imagen. Puedes añadir este código en el HTML:

```html
<!-- Botones para redimensionar la imagen -->
<div>
  <button id="boton-mas">+</button>
  <button id="boton-menos">-</button>
</div>
```

Pega este código dentro de una etiqueta `<script>` justo antes del cierre de `</body>` en el archivo HTML:

```html

<script>
  const imagen = document.getElementById('imagen-ejemplo');
  const botonMas = document.getElementById('boton-mas');
  const botonMenos = document.getElementById('boton-menos');

  // Tamaño inicial
  let ancho = 400;
  let alto = 400;

  function actualizarTamaño() {
    imagen.style.width = ancho + 'px';
    imagen.style.height = alto + 'px';
    console.log(`📏 Nuevo tamaño: ${ancho}px x ${alto}px`);
  }

  botonMas.addEventListener('click', () => {
    ancho += 20;
    alto += 20;
    actualizarTamaño();
  });

  botonMenos.addEventListener('click', () => {
    ancho = Math.max(20, ancho - 20); // Evitar tamaño negativo
    alto = Math.max(20, alto - 20);
    actualizarTamaño();
  });

  // Aplicar el tamaño inicial
  actualizarTamaño();
</script>
```
¿Por qué sigue apareciendo en la imagen "400x400"?

Porque en realidad estamos cambiando el tamaño de como se ve la imagen, no el tamaño de la imagen en sí. 

¿Te atreves a cambiar el código para que se descargue la imagen de 'https://placehold.co/400x400' con el tamaño concreto en cada caso?

---

### 🧠 Ejercicio propuesto

¿Podrías poner otro botón para restaurar el tamaño inicial de la imagen?



# 🏋️ Ejercicios 


## Ejercicio 1 - 🧙‍♂️ Manipulación del DOM: Crear y extender una tabla

### Objetivo

Añadir un elemento nuevo a una tabla ya existente. Primero debes añadir una tabla nueva que ofrecemos abajo como ejemplo y un botón en tu código `HTML`

---

### Tabla de ejemplo (a insertar desde JavaScript)

Añade esta tabla a tu código HTML, justo antes de la etiqueta `</body>`:

```html
<table>
  <thead>
    <tr>
      <th>Artefacto</th>
      <th>Descripción</th>
      <th>Nivel de poder</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Café de los 16 cores</td>
      <td>Despierta hasta al compilador más lento</td>
      <td>9000</td>
    </tr>
    <tr>
      <td>Teclado de Mithril</td>
      <td>Escribe código limpio por sí solo</td>
      <td>8800</td>
    </tr>
    <tr>
      <td>Pantalla Ultracósmica</td>
      <td>Soporta 42 ventanas abiertas sin desordenarse</td>
      <td>8600</td>
    </tr>
    <tr>
      <td>Ratón de precisión élfica dpi infinito</td>
      <td>Apunta justo al pixel del bug</td>
      <td>8450</td>
    </tr>
    <tr>
      <td>Post-it persuasivo</td>
      <td>Jamás se despega y te recuerda tus tareas pendientes más que una madre.</td>
      <td>8300</td>
    </tr>
  </tbody>
</table>
```



---

### 🧩 Instrucciones para realizar el ejercicio

1. **Crear un botón en el HTML**  
   Añade un botón al `body` con un `id` único, por ejemplo `btn-anadir-fila`, y un texto llamativo como "Añadir objeto épico".

2. **Escribir el script JavaScript que haga lo siguiente**:
   - Utiliza `document.createElement()` para crear una tabla (`<table>`) y sus elementos hijos (`<thead>`, `<tbody>`, `<tr>`, `<td>`...).
   - Asigna un `id` a la tabla, por ejemplo `tabla-epica`, para poder referenciarla más adelante.
   - Inserta la tabla al final del `<body>` o en una sección específica con `appendChild()` o `insertBefore()`.

3. **Rellenar la tabla con los datos proporcionados arriba**:
   - Crea la fila de cabecera con los títulos: *Artefacto*, *Descripción*, *Nivel de poder*.
   - Añade las 5 filas iniciales correspondientes a los objetos épicos.
   - Todo esto se puede hacer usando bucles y arrays si quieres practicar.

4. **Capturar el evento del botón**:
   - Usa `addEventListener()` sobre el botón con `click` como evento.
   - Dentro del manejador, añade una nueva fila al `tbody` de la tabla.
   - Puedes usar una lista predefinida de objetos extra para insertar de uno en uno o simplemente una fila con contenido fijo tipo:
     - *Debugger Místico*, *Encuentra bugs antes de que aparezcan*, *9999*

5. **Pistas de funciones útiles a utilizar**:
   - `document.getElementById()`
   - `document.createElement()`
   - `element.appendChild()`
   - `element.addEventListener()`
   - `createTextNode()` o `textContent`
   - `querySelector('tbody')` para acceder directamente al cuerpo de la tabla

6. **Opcional (nivel 🧠++):**
   - Alterna el color de fondo de las filas nuevas.
   - Añade una alerta cada vez que se agregue un nuevo artefacto, usando `alert()` o mejor aún, creando un mensaje dinámico en el DOM.


📝**Nota**: Este ejercicio se considerará inválido si el elemento que añadas no alcanza un nivel de epicidad y bizarría absolutamente descomunal. 😛

## 🎨 Manipulación de estilos con Bootstrap y el DOM

### Objetivo

Aplicar y modificar estilos dinámicamente usando clases de [Bootstrap 3](https://getbootstrap.com/docs/3.4/css/) desde JavaScript, a través de la manipulación del DOM. Vamos a convertir una lista en un panel dinámico con botones que alteran el estilo visual y comportamiento del contenido.

---

### 🛠 Preparación del entorno

1. **Añade Bootstrap 3 a tu `<head>`**  
   Copia este enlace antes de cerrar la etiqueta `</head>` de tu HTML:

```html
<!-- Bootstrap CSS -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">

<!-- Bootstrap JavaScript (jQuery es necesario) -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
```

2. **Añade los siguientes elementos HTML dentro del `<body>`** justo al final del HTML:

   ```html
   <div id="panel-contenedor" class="container">
     <div id="panel-estilo" class="panel panel-default">
       <div class="panel-heading">Control de estilo</div>
       <div class="panel-body">
         <ul id="panel-lista" class="list-group">
           <li class="list-group-item">Elemento mágico 1</li>
           <li class="list-group-item">Elemento mágico 2</li>
           <li class="list-group-item">Elemento mágico 3</li>
         </ul>
         <button id="btn-color" class="btn btn-primary">Cambiar color</button>
         <button id="btn-resaltar" class="btn btn-warning">Resaltar elementos</button>
         <button id="btn-reset" class="btn btn-danger">Resetear estilo</button>
        <div id="mensaje" class="mensaje-estilo text-info"></div>
       </div>
     </div>
   </div>
   ```

---
## 🧾 Instrucciones detalladas de los botones

### 🎯 Objetivo general

Modificar dinámicamente el aspecto visual de un panel y su contenido usando **clases de Bootstrap 3** mediante el **DOM en JavaScript**.

---

### 🔘 ¿Qué hace cada botón?

| Botón | Acción esperada | Estilo afectado | Comportamiento adicional |
|-------|------------------|------------------|---------------------------|
| **Cambiar color** | Alterna entre los estilos `panel-default` (gris) y `panel-info` (azul claro) | El contenedor `panel-estilo` cambia de color | Muestra el mensaje: *"🎨 ¡Color del panel cambiado!"* |
| **Resaltar elementos** | Resalta los elementos impares (0, 2, ...) de la lista con la clase `active` de Bootstrap | Los `<li>` impares dentro de `panel-lista` | Muestra el mensaje: *"✨ Elementos impares resaltados"* |
| **Resetear estilo** | Vuelve todo a su estado original: panel gris, sin resaltado | Elimina todas las clases añadidas dinámicamente | Muestra el mensaje: *"🔄 Estilos reseteados"* |

---

### 📜 Instrucciones para el script JavaScript

1. **Captura los elementos relevantes con `getElementById`**:
   - El panel: `panel-estilo`
   - La lista: `panel-lista`
   - Botones: `btn-color`, `btn-resaltar`, `btn-reset`

2. **Asigna `addEventListener` a cada botón con una función distinta**:
   - `btn-color`: alterna las clases `panel-default` ↔ `panel-info`
   - `btn-resaltar`: añade la clase `active` a los elementos impares de la lista (`li`)
   - `btn-reset`: quita todas las clases añadidas y vuelve al estilo original

3. **Funciones útiles**:
   - `element.classList.add()` / `.remove()` / `.toggle()`
   - `querySelectorAll('li')`
   - `forEach` o bucle `for` con índice para elementos impares

---

### 🧠 Extra (opcional)

- Muestra un mensaje de alerta o añade un `<div>` con texto dinámico (como "¡Estilo cambiado!") cada vez que se pulse un botón.
- Añade un botón que permita añadir más elementos a la lista con clases `list-group-item`.

---

### 🧪 Ejemplo de función JavaScript para cambiar color:

```javascript
document.getElementById("btn-color").addEventListener("click", function() {
  const panel = document.getElementById("panel-estilo");
  panel.classList.toggle("panel-default");
  panel.classList.toggle("panel-info");
});
```

---

🎯 **Reto**: adapta este sistema para permitir seleccionar el color del panel desde un `<select>` desplegable con clases como `panel-success`, `panel-danger`, etc. (nivel alto).

