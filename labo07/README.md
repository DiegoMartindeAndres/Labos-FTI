# 🧪 Laboratorio 7: jQuery y AJAX.

---

## 📚 Parte 1:  jQuery

### ✅ Introducción:

En esta parte del laboratorio aprenderemos cómo manipular jQuery, y realizaremos algunos ejercicios para practicar su utilización.
jQuery es una biblioteca de JavaScript que simplifica la manipulación del DOM, la gestión de eventos, las animaciones y las peticiones AJAX. Su sintaxis concisa permite escribir menos código y lograr resultados complejos de forma eficiente y compatible con múltiples navegadores. En este laboratorio aprenderás a utilizar jQuery para dinamizar páginas web, interactuar con elementos HTML y responder a acciones del usuario con facilidad.


---

### 🔹 1. Introducción a jQuery:

[jQuery](https://jquery.com/) es una biblioteca de JavaScript que simplifica la manipulación del DOM, eventos, AJAX y más.

Para empezar a usar jQuery en tu página, solo necesitas incluir el siguiente enlace en la sección <head> o antes del cierre del <body> de tu documento HTML:
```html
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```
Esto carga la biblioteca jQuery desde su CDN oficial.

---

###  🔹 1.2 Selectores básicos:

```javascript
$("#id")             // Selecciona por ID
$(".clase")          // Selecciona por clase
$("div")             // Selecciona por etiqueta
```

---

###  🔹 1.3  Manipulación del DOM:

```javascript
$("#titulo").text("Nuevo texto");
$("#caja").css("color", "red");
$("#lista").append("<li>Elemento nuevo</li>");
```

---

###  🔹 1.4 Manejo de eventos:

```javascript
$("#boton").click(function() {
  alert("¡Hiciste click!");
});

$("#input").on("input", function() {
  console.log($(this).val());
});
```
---

### 📎 1.5 Ejemplo guiado: 

[🌐 Ver Mundo Capibara ](code/capibaras.zip)


## Instrucciones 📝

1. **Descarga el fichero ZIP** y descomprímelo en una carpeta de tu elección, ya que ahí comenzaremos a trabajar.

2. **Antes de comenzar con los ejercicios**, es importante que revises el ejemplo guiado que hemos preparado para ti:

   - Abre el archivo `index.html` en tu navegador.
   - Interactúa con la página y observa el comportamiento de algunos botones.
   - Luego, abre de nuevo el archivo `index.html`, esta vez con un editor de texto o código (ya sabéis que recomendamos Visual Studio Code), y revisa detenidamente las siguientes partes:

     - ✅ Cómo se incluye **jQuery** desde un **CDN**.
     - ✅ El uso de **selectores** en jQuery:
       - `$("#id")`
       - `$("elemento")`
       - `$(".clase")`
     - ✅ La **manipulación del DOM** con métodos como:
       - `.text()`
       - `.css()`
       - `.fadeIn()`
     - ✅ El **manejo básico de eventos**, por ejemplo:
       - `.click()`


---

### 🔹 2. 🛠️ Ejercicios para practicar jQuery:

Emplea tus conocimientos para resolver los siguientes ejercicios (intentadlos hacer primero antes de ver las soluciones 😉):

---

<strong>- Ejercicio 1: </strong> crea un botón que al hacer clic encima de él cambie su color a otro distinto de forma aleatoria.
🎯 Una ayuda:
```html
<button id="cambiarColor">Cambiar color</button>
<div id="caja" style="width:100px;height:100px;background:gray;"></div>
```
---

<strong>- Ejercicio 2: </strong> agrega un nuevo ítem a la lista cada vez que se pulse el botón, usando el valor del input. Para ello emplea:
```html
<input type="text" id="nuevoItem">
<button id="agregar">Agregar</button>
<ul id="lista"></ul>
```

---

<strong>- Ejercicio 3: </strong> Cuenta los caracteres escritos en tiempo real.
🎯 Una ayuda: 
```html
<input type="text" id="entrada">
<p>Caracteres: <span id="contador">0</span></p>
```
---


<details>
  <summary>🧩 SOLUCIONES: 🧩</summary>
<br>


- Ejercicio 1:
```javascript
$("#cambiarColor").click(function() {
  let color = "#" + Math.floor(Math.random()*16777215).toString(16);
  $("#caja").css("background-color", color);
});
```
- Ejercicio 2:
```javascript
$("#agregar").click(function() {
  let texto = $("#nuevoItem").val();
  if (texto !== "") {
    $("#lista").append("<li>" + texto + "</li>");
    $("#nuevoItem").val("");
  }
});
```
- Ejercicio 3:
```javascript
$("#entrada").on("input", function() {
  let longitud = $(this).val().length;
  $("#contador").text(longitud);
});
```

</details>
<br>

---
<strong>🚀 Ejercicio extra (opcional) 🚀</strong>

Desafío: Crea un sistema tipo "To-do list" donde:

- Se pueda añadir tareas

- Se puedan marcar como completadas (tachadas)

- Se puedan eliminar

---



## 📚 Parte 2:  AJAX

## Objetivo
Este laboratorio te permitirá realizar tus primeras peticiones AJAX utilizando `XMLHttpRequest`. Trabajaremos con distintas APIs reales para poner en práctica los conocimientos teóricos que has adquirido.

---

## 🔧 Preparación
Crea un archivo HTML con la siguiente estructura base, que te servirá para probar cada ejercicio:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Laboratorio AJAX</title>
</head>
<body>
  <h1>Laboratorio AJAX</h1>
  <div id="resultado"></div>
  <form id="catForm" enctype="multipart/form-data">
    <input type="file" id="catImage" />
    <button type="submit">Subir imagen</button>
  </form>
</body>
</html>
```

---

## Ejercicios

### 🔹 1. Foto aleatoria de gato (API Cat)
Crea una función que haga una petición GET a `https://api.thecatapi.com/v1/images/search` para obtener una imagen aleatoria de gato y mostrarla dentro del div "resultado".

---

### 🔹 2. Subir foto de gato (API Cat)
Usa el mismo API para subir una imagen (POST). Puedes usar esta URL de ejemplo (necesitarás una API key):
`https://api.thecatapi.com/v1/images/upload`

```javascript
document.getElementById('catForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const file = document.getElementById('catImage').files[0];
  const formData = new FormData();
  formData.append('file', file);

  //añadir el codigo necesario

  xhr.send(formData);
});
```

---

### 🔹 3. Prueba a hacer una peticion (RandomDuck)
Intenta hacer una petición GET a `random-d.uk/api/random`.

📌 Observa qué error aparece en la consola. ¿A qué se debe?

---

### 🔹 4. Personaje de Rick and Morty
Usando la API de Rick and Morty (`https://rickandmortyapi.com/api`), crea una función que reciba un ID y devuelva los datos de ese personaje. Debes leer la documentación para descubrir cómo hacerlo.

---

<details>
  <summary>Soluciones 🤔</summary>
<br>

### 1. Foto aleatoria de gato
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.thecatapi.com/v1/images/search');
xhr.onload = function() {
  const data = JSON.parse(xhr.responseText);
  const img = document.createElement('img');
  img.src = data[0].url;
  img.width = 300;
  document.getElementById('resultado').appendChild(img);
};
xhr.send();
```

### 2. Subir foto de gato
```javascript
document.getElementById('catForm').addEventListener('submit', function(e) {
  e.preventDefault();
  const file = document.getElementById('catImage').files[0];
  const formData = new FormData();
  formData.append('file', file);

  const xhr = new XMLHttpRequest();
  xhr.open('POST', 'https://api.thecatapi.com/v1/images/upload');
  xhr.setRequestHeader('x-api-key', 'TU_API_KEY');
  xhr.onload = function () {
    console.log(xhr.responseText);
    document.getElementById('resultado').textContent = xhr.responseText;
  };
  xhr.send(formData);
});
```

### 3. Personaje de Rick and Morty
```javascript
function getRickAndMortyCharacter(id) {
  const xhr = new XMLHttpRequest();
  xhr.open('GET', `https://rickandmortyapi.com/api/character/${id}`);
  xhr.onload = function() {
    if (xhr.status === 200) {
      const character = JSON.parse(xhr.responseText);
      console.log('Personaje:', character);
    } else {
      console.error('Error:', xhr.status);
    }
  };
  xhr.send();
}
```

</details>
<br>

## Ejemplo de cómo combinar jQuery y AJAX.

A continuación  observaremos como utlizar de forma conjunta tanto jQuery con AJAX:

> ⚠️ **¡Atención!**  
> Debes reemplazar la constante `API_KEY` en tu código JavaScript con el API key que generaste en los laboratorios anteriores para poder acceder correctamente a **The Cat API**.



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gatos</title>
    <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>
</head>
<body>
    <img id="fotoGato" src="" alt="Gato">
    <script>
        $(document).ready(function() {
            $.ajax({
                url: "https://api.thecatapi.com/v1/images/search",
                method: "GET",
                success: function(datos) {
                    $("#fotoGato").attr("src", datos[0].url);
                },
                error: function(xhr, status, error) {
                    console.error("Error:", error);
                }
            });
        });
    </script>
</body>
</html>
```


```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Subir imagen a CatAPI</title>
    <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>
</head>
<body>
    <h1>Subir imagen a CatAPI</h1>
    
    <input type="file" id="imagenGato" accept="image/*">
    <button id="subirImagen">Subir imagen</button>
    
    <div id="resultado">
        <p>URL de la imagen: <span id="urlImagen"></span></p>
        <img id="imagenPrevisualizacion" src="" alt="Previsualización" style="max-width: 300px; display: none;">
    </div>

    <script>
        const API_KEY = 'API-KEY'; // Reemplaza con tu API Key de The Cat API

        $(document).ready(function() {
            $('#subirImagen').click(function() {
                const fileInput = $('#imagenGato')[0];
                const file = fileInput.files[0];
                
                if (!file) {
                    alert('Por favor selecciona una imagen primero');
                    return;
                }

                const formData = new FormData();
                formData.append('file', file);
                
                $('#urlImagen').text('Subiendo imagen...');
                
                $.ajax({
                    url: 'https://api.thecatapi.com/v1/images/upload',
                    method: 'POST',
                    headers: {
                        'x-api-key': API_KEY
                    },
                    data: formData,
                    processData: false,
                    contentType: false,
                    success: function(respuesta) {
                        $('#urlImagen').text(respuesta.url);
                        $('#imagenPrevisualizacion').attr('src', respuesta.url).show();
                        console.log('Imagen subida correctamente:', respuesta);
                    },
                    error: function(xhr) {
                        console.error('Error al subir la imagen:', xhr.statusText);
                        $('#urlImagen').text('Error al subir la imagen: ' + xhr.statusText);
                    }
                });
            });
        });
    </script>
</body>
</html>

```


