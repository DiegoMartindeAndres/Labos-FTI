
# 🧪 Laboratorio 09: Uso de fetch 

## 🧭 Introducción 

Bienvenidos al laboratorio de fetch 🌐. En este laboratorio vamos a usar el servicio de fetch para interactuar con varios servidores web, ya sea para obtener recursos 📦, manipularlos 🔧 o crearlos 🛠️. A lo largo del laboratorio se plantearán una serie de ejercicios 🧠 para descubrir todas las funcionalidades de fetch. 

### 📌 Objetivo

- 📤 Aprender a utilizar fetch  
- 🔗 Interactuar con APIs REST  
- 📬 Enviar, recibir y manejar datos  

### 💭 Recuerda 

Fetch es un servicio que nos permite realizar solicitudes a un servidor web sin necesidad de usar XMLHttpRequest 🚫📡. 

### 💻 Sintaxis general de una petición fetch 

```js
fetch('https://api.example.com/data', {
    method: 'GET', // Método de la solicitud
    headers: {
        'Content-Type': 'application/json', // Tipo de contenido
        'Authorization': 'tu-token-aquí' // Token de autorización
    }
})
.then(response => {
    if (!response.ok) {
        throw new Error(`Error HTTP: ${response.status}`);
    }
    return response.json(); // Procesar la respuesta como JSON. Devuelve una promesa, por eso hay otro .then debajo
})
.then(data => {
    console.log('Datos recibidos:', data); // Manejar los datos recibidos
})
.catch(error => {
    console.error('Hubo un problema con la solicitud:', error);
});

```

- <code> fetch('https://api.example.com/data', {...}) </code>:
   - <code>URL</code> 🌐: 'https://api.example.com/data' es la dirección a la que se envía la solicitud. Puede ser cualquier endpoint de API que desees consultar.
   - <code>Objeto de Opciones</code> ⚙️: El segundo argumento es un objeto que contiene las opciones de la solicitud, como el método, los encabezados, etc.

- <code> method:'GET'</code> 📨: Especifica el método HTTP a utilizar. En este caso, GET se usa para solicitar datos del servidor. Otros métodos comunes incluyen POST, PUT, DELETE, etc.

- <code> headers </code> 🧾:
   - <code> Content-Type </code>: <code>'application/json'</code> 📄: Indica el tipo de contenido que se envía o espera recibir. `application/json` es común cuando se trabaja con APIs que devuelven datos en formato JSON.
   - <code>Authorization</code>: <code>'tu-token-aquí'</code> 🔐: Se utiliza para enviar un token de autorización si la API requiere autenticación. `Bearer` es un esquema de autorización comúnmente utilizado con tokens JWT.
   - ✅ Podemos especificar tantas líneas de cabecera como queramos.

- <code> .then(response => {...}) </code> 🔄:
   - 💡 Manejo de la respuesta: La promesa devuelta por `fetch` se resuelve con un objeto `Response`. Aquí se verifica si la respuesta es exitosa (`response.ok`).
   - <code>response.json()</code> 🧪: Convierte la respuesta en un objeto JSON. Esto también devuelve una promesa.

- <code> .then(data => {...}) </code> 📊: **Manejo de los Datos**: Aquí se manejan los datos JSON recibidos del servidor. Puedes realizar cualquier operación con estos datos, como mostrarlos en la consola o actualizar la interfaz de usuario.

- <code> .catch(error => {...}) </code> ⚠️: **Manejo de Errores**: Captura cualquier error que ocurra durante la solicitud, como problemas de red o errores HTTP, y lo registra en la consola.

### 🛠️ Herramientas 
Los siguientes ejercicios se pueden realizar con las siguientes herramientas: 
- 🧪 La consola de un navegador (Chrome, Mozilla, Opera...)
- 💻 Visual Studio Code (recomendado)


## 🧩 Ejercicios

### 🚀 ¿Cómo usar el código que te proporcionamos?

Tienes varias formas de ejecutar el código:

- **Opción rápida:** Puedes copiarlo directamente en la consola de tu navegador.
- **Opción recomendada:** Usa Visual Studio Code para integrarlo dentro de un archivo `.html`. Así podrás modificarlo, guardarlo y ejecutarlo cómodamente desde el navegador.

A continuación te proporcionamos una plantilla básica para comenzar con el **primer ejercicio**. A medida que avances, podrás modificar este archivo para resolver los distintos ejercicios propuestos:

📄 [Ver archivo base `pruebas.html`](code/pruebas.html)

---

### 📚 Consulta la documentación de la API

Antes de empezar con cada ejercicio, es fundamental que **revises la documentación** de la API que vas a utilizar. Esto te ayudará a entender qué datos puedes obtener y cómo hacerlo correctamente.

🔗 [Accede a la documentación de la API REST Countries](https://restcountries.com/#api-endpoints)

### 1️⃣ Obtener datos de una API pública (GET) 
La API <code> restcountries </code> 🌍 nos permite consultar información sobre , países 🗺️. 

#### 🧪 Ejemplo
 

```js
fetch('https://restcountries.com/v3.1/name/spain')
  .then(res => res.json())
  .then(data => {
    console.log(data[0].name.common); // Muestra "Spain"
  })
  .catch(error => console.error('Error:', error));
```

#### 📖 Explicación del ejemplo 

<ol>
  <li><code>fetch('https://restcountries.com/v3.1/name/spain')</code> 🌍: 
  <ul>
    <li>Hacemos una petición GET al servicio <code>http://restcountries.com</code> 🌐</li>
    <li>El endpoint <code>/v3.1/name/spain</code> 🔎 busca los datos del país llamado "spain" (podríamos especificar cualquier otro país)</li>
  </ul>  
  </li>
  <li><code>.then(res => res.json())</code> 🔄
  <ul>
    <li><code>fetch</code> devuelve una promesa que se resuelve con un objeto de respuesta <code>(res)</code> 📦</li>
    <li><code>res.json()</code> también devuelve una promesa, que se resuelve con los datos de la respuesta convertidos a un objeto JavaScript 🧠 (porque el servidor devuelve JSON)</li>
  </ul>
  </li>
  <li><code>.then(data => {...})</code> 📊
  <ul>
    <li>Recibimos los datos de la API en formato objeto (o array de objetos) 📁</li>
    <li>En este caso, <code>data</code> es un array porque puede haber más de un país que coincida con el nombre buscado (aunque generalmente es solo uno) 🔁</li>
    <li><code>data[0]</code> accede al primer resultado 🔢</li>
    <li><code>data[0].name.common</code> accede al nombre común del país, que en este caso es <code>"Spain"</code> 🇪🇸</li>
  </ul>  
  </li>
  <li><code>.catch(error => console.error('Error:', error));</code> ⚠️:  
    Si ocurre cualquier error (por ejemplo, si no hay conexión o la API devuelve un fallo), este bloque lo captura y lo imprime en la consola 🛠️
  </li>
</ol>

**📝 Ejercicios**

1. Obtén la capital de España.
2. Obtén la bandera de España.
3. Obtén la población de España.
4. Obtén como se llama España en japonés.
5. Elije cualquier país 🌎 y muestra su nombre 🏷️, su bandera 🏳️, su capital 🏛️ y su población 👥.  


---

### 2️⃣ Enviar datos a un servidor 📤

Vamos a enviar datos de un formulario 📝 a un servidor web, por ejemplo para crear un usuario 👤.

#### 🧪 ¿Qué API vamos a usar?

Para estos ejercicios utilizaremos la API de [`jsonplaceholder`](https://jsonplaceholder.typicode.com/), una API de prueba que **simula el comportamiento de un servidor web real**.

Aunque responde como si almacenara datos, **no guarda permanentemente la información que le envías**. Por eso es perfecta para hacer pruebas y experimentar sin miedo a romper nada ni perder datos. Ideal para aprender y practicar con llamadas `GET`, `POST`, `PUT` y `DELETE`.


### 📖 Aprende a usar la API

Antes de comenzar, te recomiendo que leas la documentación para entender cómo funciona esta API de prueba y qué endpoints puedes utilizar:

🔗 [Guía de uso de JSONPlaceholder](https://jsonplaceholder.typicode.com/guide/)


> ⚠️ **Recuerda:**  
> El siguiente código está pensado para ejecutarse directamente en la **consola del navegador**.  
> 
> Si decides integrarlo dentro de un archivo HTML, como ya sabes, **deberás modificar el DOM** (por ejemplo, con `document.getElementById()`, `innerHTML`, etc.) para poder mostrar los resultados en la página. Obviamente, también puedes usar `jQuery` o cualquier otra librería que prefieras. Demuestrate que puedes hacerlo tú solo/a. 😉


```js
const userData = {
  username: "alumno1",
  email: "alumno1@example.com"
};

fetch('https://jsonplaceholder.typicode.com/users', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(userData)
})
  .then(res => res.json())
  .then(data => console.log(data));
```

#### 📖 Explicación del ejemplo 

<ol>
  <li>🧾 Definimos el objeto que contiene la información que queremos mandar al servidor</li>
  <li>🌐 Hacemos la petición a la URL <code>https://jsonplaceholder.typicode.com/users</code> con el <code>endpoint</code></li>
  <li>📬 Indicamos el método (<code>POST</code>) y los <code>headers</code> adecuados</li>
  <li>🔄 Convertimos el objeto a <code>JSON</code> e incluimos el objeto que hemos creado antes en el <code>body</code> para mandarle la información al servidor</li>
  <li>📥 Recibimos la respuesta y la mostramos por pantalla 🖥️</li>
</ol>

**📝 Ejercicio**

Crea un formulario simple 🧍‍♂️📄 para registrar un usuario ficticio y muestra el resultado por pantalla 🎯.  

---

### 3️⃣ Obtener datos de un blog 📰

Vamos a solicitar los datos de un blog a un servidor web 📡 y a mostrarlos por pantalla 👁️.

```js
fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => response.json())
  .then(posts => {
    posts.slice(0, 5).forEach(post => {
      console.log(`📌 ${post.title}\n📝 ${post.body}\n`);
    });
  })
  .catch(error => console.error('Error al obtener las publicaciones:', error));
```

#### 📖 Explicación del ejemplo 
<ol>
    <li><code>fetch('https://jsonplaceholder.typicode.com/posts')</code> 📡: Solicitamos los datos a un servidor usando el servicio fetch. En este caso usamos como método GET 📨</li>
    <li><code>.then(response => response.json())</code> 🔄: Convertimos la respuesta del servidor en un objeto para manejarlo mejor 🧠.</li>
    <li><code>.then(posts => { ... })</code> 📝: De las publicaciones obtenidas tomamos solo las cinco primeras publicaciones 📃.</li>
    <li><code>posts.slice(0, 5).forEach(post => { ... })</code> 👁️: Imprimimos los datos por pantalla 🖥️.</li>
</ol>

**📝 Ejercicio**

### 🐶 ¡También hay una API para perros!

¿Os acordáis de **The Cat API**?  
Pues no vamos a cometer **racismo animalario** 🐾 — también existe una API para **perros**:  
🔗 [https://dog.ceo/](https://dog.ceo/)

La vamos a usar para **obtener imágenes aleatorias de perros** y practicar con `fetch`.

---

📖 **Importante:**  
Aunque sé que no hace falta que te lo diga… por si acaso:  
**Lee la documentación de la API** para saber cómo funciona, qué endpoints puedes usar y qué tipo de respuesta devuelve.

🔗 [Documentación oficial de Dog API](https://dog.ceo/dog-api/documentation/)



🐶 Prueba a obtener varias imágenes aleatorias sobre perros en esta URL:  
👉 https://dog.ceo/api/breeds/image/random

La solicitud te devolverá varios enlaces aleatorios para que puedas consultar las imágenes siempre que quieras 📷.

❓ **Pista**  
- Para solicitar varias imágenes utiliza una variable auxiliar y un bucle <code>for</code> 🔁 para solicitar todas las imágenes que quieras.  
- No es necesario utilizar las funciones <code>forEach()</code> o <code>slice()</code> en este ejercicio 🚫.

### 🦫 ¿Y una API de capibaras?

¿Crees que habría una API para capibaras?  
— **Of course!** 😎

🔗 [Capybara API](https://capy.lol/)

Esta API te permite [obtener imágenes aleatorias de la criatura más relajada del reino animal](https://api.capy.lol/v1/capybara). Ideal para seguir practicando tus llamadas `fetch` mientras sonríes un poco.

---

### 4️⃣ Eliminar datos de un servidor 🗑️

Vamos a usar `fetch` para eliminar un recurso de un servidor ⚙️.  
⚠️ **OJO** → Normalmente las páginas no permiten eliminar recursos, en este caso estamos utilizando una API que **sí** nos lo permite 🧪. Bueno, en realidad no, te dice que lo hacer para hacer pruebas, pero en realidad no lo ejecuta.

```js
fetch('https://jsonplaceholder.typicode.com/posts/1', {
  method: 'DELETE'
})
  .then(res => {
    if (res.ok) {
      console.log('Recurso eliminado');
    }
  });
```

#### 📖 Explicación del ejemplo 
<ol>
    <li><code>fetch('https://jsonplaceholder.typicode.com/posts/1')</code> 🧭: Especificamos la URL de la que queremos eliminar el recurso 🔗.</li>
    <li><code>method</code>: <code>DELETE</code> 🗑️: Con este método vamos a indicar al servidor que queremos eliminar el recurso especificado en la URL 🚫.</li>
    <li>✅ Si la solicitud ha sido acertada mostramos un mensaje de que el recurso ha sido eliminado con éxito 📬.</li>
</ol>

**📝 Ejercicio**  

Construye una petición `fetch` 🧪 para eliminar un usuario aleatorio de esta API:  
🔗 `'https://reqres.in/api/users/'`  
Pon un número aleatorio después de <code>/users/</code> 🎲.

### 🤔 ¿No sabes cómo funciona una API nueva?

— *Vaya... me pregunto qué podríamos hacer en ese caso...* 🙄  
(Spoiler: **¡leer la documentación!** 📚)

Para practicar con APIs y simular usuarios, logins, y otras operaciones comunes, puedes usar esta API de pruebas:

🔗 [Reqres API](https://reqres.in/)

Es ideal para experimentar con peticiones `GET`, `POST`, `PUT`, y `DELETE` sin miedo a romper nada.

🔐 **Bonus:**  
Puedes registrarte para obtener una **API Key** y así desbloquear peticiones más avanzadas o personalizadas. Esto es muy útil cuando empieces a trabajar con APIs reales que requieren autenticación.


---

### 5️⃣ Uso de fetch con async/await ⏳

Vamos a combinar el uso de `fetch` para solicitar un recurso a un servidor 🌐 y las funciones <code>async/await</code> para manejar funciones asíncronas 🚀.


```js
async function obtenerDatos() {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts');
    const data = await res.json();
    console.log(data);
  } catch (error) {
    console.error('Error al obtener datos', error);
  }
}

obtenerDatos();
```

#### 📖 Explicación del ejemplo 

<ol>
    <li>🔧 Definimos la función <code>async</code>: gracias a esta función especificamos que es una función asíncrona ⚙️ y que por tanto podemos usar <code>await</code> dentro de ella ⏳.</li>
    <li>🧯 Bloque <code>try/catch</code>: para manejar los posibles errores que puedan ocurrir durante la ejecución 🔁.</li>
    <li><code>await fetch(...)</code> 🌐: Hacemos la solicitud HTTP GET usando <code>fetch</code> y <code>await</code> para pausar la ejecución hasta que se resuelva la promesa ⏸️.</li>
    <li><code>await res.json()</code> 🧪: Usamos un <code>await</code> para pausar la conversión de la respuesta del servidor a formato JSON 📦.</li>
    <li>🖨️ Una vez resueltas todas las promesas, imprimimos la información por consola 🖥️.</li>
    <li>📲 Llamamos a la función para mostrar los datos en pantalla 👀.</li>
</ol>

**📝 Ejercicio**

Envía una petición a la siguiente API:  
🔗 <a href="https://pokeapi.co/api/v2/pokemon/">API Pokémon</a>  
para obtener los datos de un Pokémon que pasamos como parámetro a la función <code>obtenerDatos()</code> 🧬.  

Usa la estructura del ejemplo para que sea una función asíncrona 🚀.


⚠️La URL que tienes que poner en la petición fetch es: "https://pokeapi.co/api/v2/pokemon/${pokemon}", siendo {pokemon} el parámetro que pasamos a la función obtenerDatos();

### Ejercicio 6 📖

Utilizando la API de gatos (https://thecatapi.com/), realiza las siguientes solicitudes:

1. Obtener razas de gatos: Recupera información sobre las razas de gatos disponibles.

2. Filtrar por origen: Busca las razas de gatos que provienen de un país específico (usa el parámetro country_code).

3. Usa una API Key para autenticar las solicitudes.

4. Muestra los resultados en la consola del navegador.

<details>
  <summary>¿No sabes cómo hacerlo?</summary>

```javascript
// API Key para la autenticación
const apiKey = 'TU_API_KEY_AQUÍ'; // Reemplaza con tu API Key

// Obtener todas las razas de gatos
const fetchCatBreeds = () => {
  fetch('https://api.thecatapi.com/v1/breeds', {
    headers: {
      'x-api-key': apiKey
    }
  })
    .then(response => {
      if (!response.ok) {
        throw new Error(`Error en la solicitud: ${response.status}`);
      }
      return response.json();
    })
    .then(data => {
      console.log('Razas de gatos disponibles:', data.map(breed => breed.name));
    })
    .catch(error => console.error(error));
};

// Filtrar razas por país de origen
const fetchBreedsByCountry = (countryCode) => {
  fetch('https://api.thecatapi.com/v1/breeds', {
    headers: {
      'x-api-key': apiKey
    }
  })
    .then(response => {
      if (!response.ok) {
        throw new Error(`Error en la solicitud: ${response.status}`);
      }
      return response.json();
    })
    .then(data => {
      const filteredBreeds = data.filter(breed => breed.origin === countryCode);
      console.log(`Razas de gatos originarias de ${countryCode}:`, filteredBreeds.map(breed => breed.name));
    })
    .catch(error => console.error(error));
};

// Ejecución
fetchCatBreeds(); // Para obtener todas las razas
fetchBreedsByCountry('Japan'); // Filtra razas originarias de Japón (por ejemplo)
```

</details>

### Ejercicio 7 📖



Subir una imagen de un gato mediante un formulario simple.

1. Diseña un formulario HTML con un campo de tipo `file` para que el usuario pueda seleccionar una imagen desde su dispositivo.
2. Implementa un script que:
   - Intercepte el evento `submit` del formulario.
   - Use la API de gatos para subir la imagen seleccionada (consulta la documentación de la API para la operación `POST /images/upload`).
   - Incluye en la solicitud la **API Key** para autenticación.
3. Muestra el resultado (incluyendo un mensaje de éxito o error) en el navegador.

<details>
    <summary>¿No sabes cómo hacerlo?</summary>

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Subir Imagen de Gato</title>
    </head>
    <body>
      <h1>Subir Imagen de Gato</h1>
      
      <!-- Formulario para subir imagen -->
      <form id="catForm">
        <label for="catImage">Selecciona una imagen de gato:</label>
        <input type="file" id="catImage" name="catImage" accept="image/*" required>
        <button type="submit">Subir Imagen</button>
      </form>
      
      <p id="responseMessage"></p>

      <script>
        const form = document.getElementById('catForm');
        const apiKey = 'TU_API_KEY_AQUÍ'; // Reemplaza con tu API Key
        const apiUrl = 'https://api.thecatapi.com/v1/images/upload';

        form.addEventListener('submit', async (event) => {
          event.preventDefault(); // Evita el comportamiento predeterminado del formulario

          const fileInput = document.getElementById('catImage');
          const file = fileInput.files[0]; // Obtén el archivo seleccionado
          
          if (!file) {
            alert('Por favor, selecciona una imagen para subir.');
            return;
          }

          const formData = new FormData();
          formData.append('file', file);

          try {
            const response = await fetch(apiUrl, {
              method: 'POST',
              headers: {
                'x-api-key': apiKey
              },
              body: formData
            });

            if (!response.ok) {
              throw new Error(`Error en la solicitud: ${response.status}`);
            }

            const data = await response.json();
            document.getElementById('responseMessage').textContent = 'Imagen subida con éxito: ' + data.url;
            console.log('Respuesta de la API:', data);
          } catch (error) {
            document.getElementById('responseMessage').textContent = 'Error al subir la imagen: ' + error.message;
            console.error(error);
          }
        });
      </script>
    </body>
    </html>
    ```
</details>


### Ejercicio Final 🧠

### Crear un buscador de recetas basado en ingredientes

#### Objetivo:
Utilizar la API pública [TheMealDB](https://www.themealdb.com/api.php) para buscar recetas en base a ingredientes proporcionados por el usuario.


### 🚀 Pasos a seguir:

1. **Interfaz de usuario:**
   - Diseña un formulario HTML simple que tenga:
     - Un campo de texto donde el usuario pueda ingresar un ingrediente (ejemplo: "chicken").
     - Un botón para buscar las recetas.

2. **Implementación de JavaScript:**
   - Usa `fetch` para enviar una solicitud HTTP GET a la API con el ingrediente especificado.
   - Procesa los resultados de la API (listado de recetas) y muéstralos en el navegador:
     - Puedes mostrarlos como una lista, tabla, o tarjetas con imágenes de las recetas.

3. **Operaciones a implementar:**
   - Validación del campo de entrada: Asegúrate de que el usuario ingrese al menos un ingrediente antes de realizar la solicitud.
   - Manejo de errores: Si la API no responde o no hay recetas disponibles, muestra un mensaje informativo.
   - (Opcional) Estilo adicional: Agrega CSS para mejorar la presentación de los resultados.



### 📝 Requisitos técnicos:

1. Enviar una solicitud GET con la ruta:  
   `https://www.themealdb.com/api/json/v1/1/filter.php?i=INGREDIENTE`  
   Donde `INGREDIENTE` es el texto ingresado por el usuario en el formulario.

2. Iterar sobre el resultado retornado por la API para extraer las recetas (nombre e imagen).

3. Mostrar el resultado en el navegador de forma dinámica.



### 🎯 Actividad extra:
Agrega un botón que permita al usuario buscar recetas **aleatorias** utilizando la ruta:  
`https://www.themealdb.com/api/json/v1/1/random.php`  
Muestra la receta seleccionada de forma destacada en la página.
