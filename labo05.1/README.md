# 🏋️ Ejercicios JavaScript

## ✨ Objetivos del laboratorio

El propósito de este laboratorio es que practiques la programación de algoritmos utilizando JavaScript, partiendo de un conjunto de ejercicios. No se trata solo de escribir código que funcione, sino de aplicar un **proceso sistemático de desarrollo** que te ayude a resolver problemas de forma ordenada, eficiente y profesional.

## 🧠 Antes de programar... piensa

Programar **no es solo escribir código**, sino resolver problemas. Y para resolver problemas, hay un **proceso mental** que debemos seguir antes de abrir el editor:

1. **Leer el enunciado con atención** 📄  
   > Es la fase de **Toma de requisitos**. ¿Qué nos están pidiendo? ¿Qué datos se nos dan? ¿Qué resultados se esperan?

2. **Entender el problema** 🤔  
   > Equivale al **Análisis**. ¿Qué casos pueden darse? ¿Qué limitaciones tiene el problema?

3. **Plantear una solución lógica** 🧩  
   > Esta es la fase de **Diseño**. Pensamos cómo resolverlo con un algoritmo, qué pasos seguir, y qué estructuras de datos emplear.

4. **Programar la solución** 💻  
   > Aquí comienza la **Implementación** en JavaScript. Escribimos el código basándonos en el diseño previo.

5. **Probar y depurar** 🧪  
   > Por último, llega la fase de **Pruebas**. Verificamos que el código funciona para todos los casos posibles, incluidos los límites o casos especiales.


### 🤖 ¿Y la inteligencia artificial?

Vivimos en un momento histórico donde herramientas basadas en inteligencia artificial pueden ayudarnos a programar. Es más: **puedes copiar el enunciado de estos ejercicios y pedírselo directamente a una IA**, y seguramente te devuelva una solución bastante razonable. Los enunciados están redactados de forma clara y precisa, y eso facilita mucho que una IA los entienda. Pero...

> ❗ **Esto no será lo normal en el mundo real.**

En la vida profesional, los problemas no vendrán con enunciados tan bien redactados. Te tocará enfrentarte a requisitos difusos, clientes que no saben expresar lo que quieren o necesidades que cambian sobre la marcha. **Deberás ser capaz de entender el problema, formularlo bien y plantear soluciones viables**.

Y ahora piensa:

> 🧾 ¿Y si la IA se encarga de programar por ti?  
> 💰 ¿Por qué te iban a pagar a ti?  
> 🧠 ¿Cómo justificarás tu salario?

Simplemente piénsalo.

Saber programar no es solo teclear código. Es **entender, razonar, diseñar, validar y corregir**. La IA puede ayudarte en todo ese proceso, pero **no puede hacerlo sin ti**. Por eso, **no debemos saltarnos ninguna fase del desarrollo**.


---

## Ejercicio 1 - 🧐 Verificar si una cadena comienza con 'Java'

### 📖 Descripción del ejercicio

Escribe una función en JavaScript que determine si una cadena de texto dada comienza con la palabra 'Java' (sensible a mayúsculas y minúsculas). La función debe devolver `true` si la cadena comienza con 'Java' y `false` en caso contrario.

### ✍️ Entrada

- Una cadena de texto.

### 📤 Salida esperada

- Un valor booleano: `true` si la cadena comienza con 'Java', `false` en caso contrario.

### 🧪 Ejemplos

```javascript
comienzaConJava('JavaScript'); // Resultado esperado: true
comienzaConJava('Java');       // Resultado esperado: true
comienzaConJava('Python');     // Resultado esperado: false
```


### 🧠 Pistas

🔍 Es posible que lo primero que se te ocurra sea extraer los primeros caracteres de la cadena y compararlos con la palabra 'Java'. Sin embargo...

💡 Existe un método más directo y eficiente. Pregúntate:

> ¿Hay algún método en los strings de JavaScript que permita verificar si una cadena comienza con una subcadena específica?

📖 Revisa la documentación oficial sobre los métodos de los strings en JavaScript:

[https://www.w3schools.com/js/js_string_methods.asp](https://www.w3schools.com/js/js_string_methods.asp)

---

## 🧠 Ejercicio 2 - Número más cercano a 100

🎯 **Objetivo:**  
Escribir una función que reciba dos números enteros positivos y devuelva el que esté más próximo a 100.

📥 **Entrada de ejemplo:**
- `90`, `89`

📤 **Salida esperada:**
- `90`

🔍 **Indicaciones:**
- Ambos números serán mayores que 0.
- Si ambos están a la misma distancia de 100, la función puede devolver cualquiera de ellos.

💡 **Pista:**  
Piensa en cómo calcular la **distancia** entre cada número y el 100.

---





## 🗓️ Ejercicio 3 - Determinar si un año es bisiesto en el calendario gregoriano

### Descripción del problema
Un año bisiesto en el calendario gregoriano es aquel que tiene 366 días en lugar de los 365 habituales. Esto se logra añadiendo un día extra al mes de febrero, que pasa a tener 29 días. Los años bisiestos se introdujeron para mantener la sincronización del calendario con el año astronómico o estacional
Para determinar si un año es bisiesto, se siguen estas reglas

1. Si el año es divisible por 4, pasa al paso 2. De lo contrario, no es bisiesto
2. Si el año es divisible por 100, pasa al paso 3. De lo contrario, es bisiesto
3. Si el año es divisible por 400, es bisiesto. De lo contrario, no es bisiesto
Por ejemplo, los años 2000 y 2016 son bisiestos, mientras que 1700, 1800 y 1900 no lo son

### Entrada y salida esperadas

- **Entrada:** Un número entero que representa el año (por ejemplo, 2024)
- **Salida:** Un valor booleano: `true` si el año es bisiesto, `false` en caso contrario

**Ejemplo:**

```javascript
esBisiesto(2024);
```

**Salida esperada:**

```javascript
true
```

### Diagrama de flujo

```mermaid
graph TD;
    A[Inicio] --> B{¿El año es divisible por 4?};
    B -- Sí --> C{¿El año es divisible por 100?};
    B -- No --> E[No es bisiesto];
    C -- Sí --> D{¿El año es divisible por 400?};
    C -- No --> F[Es bisiesto];
    D -- Sí --> F;
    D -- No --> E;
    E --> G[Fin];
    F --> G;
```

### ¿Cómo comprobar que tu código funciona?

Hay que hacer pruebas. De momento solo vamos a hacer `smoke tests`, es decir, comprobar que el código no tiene errores de sintaxis. Para ello, puedes copiar el código en la consola del navegador y ejecutarlo.

Las pruebas unitarias las haremos más adelante.

---

## Ejercicio 4 - 🌡️ Conversión de temperaturas entre Celsius y Fahrenheit

### 📝 Enunciado
Escribe un programa en JavaScript que convierta temperaturas entre las escalas Celsius y Fahrenhei.

### 🔍 Descripción

Las escalas Fahrenheit y Celsius son dos sistemas de medida de temperatura ampliamente utilizads.
- **Fahrenheit**: En esta escala, el agua se congela a 32 grados y hierve a 212 grads.- **Celsius**: En esta escala, el agua se congela a 0 grados y hierve a 100 grads.

Las fórmulas de conversión son:
- De Fahrenheit a Celsis:
  \[ C = \frac{5}{9} \times (F - 32)\]
- De Celsius a Fahrenhet:
  \[ F = C \times \frac{9}{5} + 32\]

### 📥 Entrada esperaa

Un número que represente la temperatura y una indicación de la escala original (Celsius o Fahrenhet).

### 📤 Salida esperda

La temperatura convertida a la escala opuesta, mostrando el valor original y el converido.

### 🧪 Casos de prueba sugerdos


```javascript
convertirTemperatura(60, 'C'); // "60°C son 140°F."
convertirTemperatura(45, 'F'); // "45°F son 7.222°C.
```


---

## Ejercicio 5: 📝 Contar el número de vocales en una cadena

**Objetivo:** Desarrollar una función en JavaScript que cuente cuántas vocales (a, e, i, o, u) hay en una cadena dada

**Instrucciones:**

1. Escribe una función que tome una cadena como entrada y devuelva el número total de vocales presentes en ella
2. Considera que la cadena puede contener letras mayúsculas y minúsculas, así como otros caracteres
3. Ten en cuenta que la solución más inmediata podría ser utilizar un bucle `for` para recorrer cada carácter de la cadena y contar las vocales. Sin embargo, existe una forma más sencilla y eficiente de lograrlo empleando los métodos de cadena y expresiones regulares en JavaScript, que permite obtener el resultado en una sola línea de código

**Pista:**
Investiga cómo utilizar el método `match` de las cadenas junto con expresiones regulares para identificar y contar caracteres específicos en una cadena

<details>
<summary>💡 Solución en una línea de código</summary>

```javascript
const contarVocales = cadena => (cadena.match(/[aeiou]/gi) || []).length;
```

**Nota:** En la solución proporcionada, la expresión regular `/[aeiou]/gi` busca todas las vocales en la cadena sin distinguir entre mayúsculas y minúsculas. El método `match` devuelve un array con todas las coincidencias, y al obtener su longitud con `.length`, se obtiene el número total de vocales. Si no se encuentran vocales, `match` devuelve `null`, por lo que se utiliza `|| []` para asegurar que siempre se trabaje con un array y evitar errore. 

</details>
<br>

**Ejemplo de uso:**

```javascript
console.log(contarVocales("JavaScript")); // Output: 3
console.log(contarVocales("w3resource.com")); // Output: 5
```

---

## 🧪 Ejercicio 6: El número más grande 🔢

### Descripción  
Queremos trabajar con arrays en JavaScript. En este ejercicio deberás implementar una función que reciba un array de números y devuelva el número **más grande** que contiene.

### 🧠 Objetivo  
Practicar el uso de estructuras de datos como arrays y afianzar el uso de bucles o métodos integrados para recorrerlos.

### ✍️ Instrucciones  
1. Crea una función con un nombre descriptivo.
2. Asegúrate de que la función reciba **un solo parámetro**, que será un array de números.
3. La función debe **devolver** el número más grande del array.
4. Puedes asumir que el array tiene al menos un número.

### 🧾 Ejemplo de entrada
```js
[3, 7, 2, 9, 5]
```

### ✅ Salida esperada
```js
9
```


---

## Ejercicio 7: 🔁 Invirtiendo un array

En este ejercicio vamos a trabajar con **arrays en JavaScript**, concretamente con la inversión de su contenido. El objetivo es que el estudiante entienda cómo manipular los elementos de un array utilizando bucles y métodos incorporados del lenguaje.

### 🎯 Objetivo

Dado un array de números, crea un nuevo array con los elementos en orden inverso.

### 📥 Entrada

Un array de números, por ejemplo:

```js
[1, 2, 3, 4, 5]
```

### 📤 Salida esperada

```js
[5, 4, 3, 2, 1]
```


### 🧠 Parte 1: Usando un bucle

Escribe una función que reciba un array y devuelva uno nuevo con los elementos en orden inverso, utilizando un bucle `for` o `while`.

- Puedes usar un array auxiliar donde vayas insertando los elementos.

> ✨ Consejo: Empieza recorriendo el array original desde el último índice hasta el primero.


### ⚙️ Parte 2: Usando el método `.reverse()`

Una vez tengas la solución usando un bucle, intenta hacer lo mismo utilizando el método `reverse()` de los arrays en JavaScript.

> 📚 Puedes consultar cómo funciona este método en la documentación oficial de MDN:  
> [Array.prototype.reverse() - MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)


---

## 🧮 Ejercicio 8 - Cálculo del área de un triángulo a partir de sus tres lados

### ✍️ Enunciado

Escribe una función en JavaScript que reciba **tres números** como parámetros, correspondientes a los tres lados de un triángulo (por ejemplo, `a`, `b` y `c`), y devuelva el **área** del triángulo usando la **fórmula de Herón**.

🔢 **Ejemplo**  
Entrada: lados `a = 5`, `b = 6`, `c = 7`  
Salida esperada: `14.6969...`

---

### 🧠 Pistas

Para resolver este ejercicio, necesitarás:

1. **Calcular el semiperímetro** del triángulo:
   
   📌 Fórmula:

   ```
   s = (a + b + c) / 2
   ```

2. **Aplicar la fórmula de Herón** para obtener el área:

   📌 Fórmula:

   ```
   área = √[s(s - a)(s - b)(s - c)]
   ```

3. Para calcular la raíz cuadrada en JavaScript, puedes usar:

   ```
   Math.sqrt(x)
   ```


---

## 🧠 Ejercicio 9 - Fechas en JavaScript

### 📋 Enunciado

Escribe una función en JavaScript que muestre en consola la **fecha y hora actual** en el siguiente formato:

```
Hoy es: Martes.
Hora actual: 10 PM : 30 : 38
```

🔹 El formato debe indicar:
- El **día de la semana** en español.
- La **hora en formato de 12 horas**, con indicación de AM o PM.
- Los **minutos** y **segundos** actuales.

---

#### 🧠 Pequeño pseudocódigo

```
1. Crear una variable con la fecha actual usando Date()
2. Crear un array con los nombres de los días de la semana
3. Obtener el número de día con getDay() y buscar el nombre en el array
4. Obtener la hora, minutos y segundos
5. Convertir la hora de 24h a 12h y añadir AM o PM
6. Imprimir el mensaje en el formato indicado
```

### 💡 Pistas

#### 📆 Uso del objeto `Date()`

JavaScript tiene un objeto nativo llamado `Date` que nos permite trabajar fácilmente con fechas y horas actuales:

```js
const ahora = new Date();
```

Este objeto tiene métodos para obtener partes específicas de la fecha, como:

- `getDay()` → devuelve el día de la semana (0 es Domingo, 1 es Lunes, ..., 6 es Sábado)
- `getHours()` → devuelve la hora en formato de 24h (de 0 a 23)
- `getMinutes()` → devuelve los minutos
- `getSeconds()` → devuelve los segundos


#### 🗓️ ¿Por qué crear un array con los días de la semana?

Porque el método `.getDay()` devuelve un **número del 0 al 6**, pero tú necesitas mostrar el **nombre del día** (“Lunes”, “Martes”, etc.).

Por eso, lo ideal es usar un array donde el índice corresponda al valor numérico de `getDay()`:

```js
const dias = ['Domingo', 'Lunes', 'Martes', 'Miércoles', 'Jueves', 'Viernes', 'Sábado'];
```

Así, puedes acceder al nombre con:

```js
const nombreDia = dias[ahora.getDay()];
```

---

## Ejercicio 10: 🎄 Días restantes hasta la próxima Navidad

Escribe un programa en JavaScript que calcule el número de días que faltan para la próxima Navidad (25 de diciembre).

**Entrada esperada:**

-La fecha actual

**Salida esperada:**

-Número de días restantes hasta el 25 de diciembre del año en curso

**Pistas:**

- Utiliza el objeto `Date` de JavaScript para obtener la fecha actual y para establecer la fecha de Navidad
- Recuerda que los meses en JavaScript se indexan desde 0 (enero) hasta 11 (diciembre)
- Si la fecha actual es posterior al 25 de diciembre, deberás calcular los días restantes hasta el 25 de diciembre del año siguiente

**Ejemplo de uso del objeto `Date`:**

```javascript
// Obtener la fecha actual
const hoy = new Date();

// Crear un objeto Date para el 25 de diciembre del año actual
const navidad = new Date(hoy.getFullYear(), 11, 25);
```

---


## 🧪 Ejercicio 11: El número más repetido

### Descripción

En este ejercicio trabajarás con arrays y estructuras de datos para analizar la frecuencia de los elementos. El objetivo es encontrar el número que más veces se repite en un array dado.

Si hay varios números con la misma frecuencia máxima, debes devolver **el que aparece primero** entre ellos.

### 🎯 Objetivo

Escribir una función en JavaScript que reciba un array de números y devuelva el número que más veces se repite.

### 📥 Entrada

Un array de números enteros, por ejemplo:

```javascript
[3, 1, 3, 2, 1, 3, 2, 1]
```

### 📤 Salida esperada

```javascript
3
```

### ℹ️ Notas

- Puedes asumir que el array no estará vacío.
- Si hay empate, se devuelve el número que **aparece antes** en el array original con la máxima frecuencia.

### 🧠 Pistas

- Considera usar objetos o estructuras [🗺️ Map](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Map) para contar apariciones.
- Piensa en cómo llevar un seguimiento del orden de aparición mientras calculas frecuencias.

---


## 🧑‍💻 Ejercicio 12: Reemplazar cada carácter en una cadena por el siguiente en el alfabeto
En este ejercicio, desarrollarás una función en JavaScript que toma una cadena de texto y reemplaza cada letra por la siguiente en el alfabeto. Además, las vocales resultantes deben convertirse a mayúscula.

### 📜 Descripción
- Cada letra en la cadena debe ser sustituida por la siguiente letra en el alfabeto. Por ejemplo, 'a' se convierte en 'b', 'b' en 'c', y así sucesivamene.
- Las vocales ('a', 'e', 'i', 'o', 'u') resultantes después de la sustitución deben transformarse a mayúsculs.
- Los caracteres no alfabéticos deben permanecer sin cambis.

### 🔍 Ejemplo

**Entrada**

```
"javascript"
```


**Proceso:** 
1. 'j' →'k'
2. 'a' → 'b' (convertido a mayúscula: B')
3. 'v' →'w'
4. 'a' → 'b' (convertido a mayúscula: B')
5. 's' →'t'
6. 'c' →'d'
7. 'r' →'s'
8. 'i' → 'j' (convertido a mayúscula: J')
9. 'p' →'q'
10. 't' → 'u' (convertido a mayúscula: U')

**Salida**

```
"kBwBtBdsJqU"
```


### 🛠️ Instrucciones
1. Crea una función en JavaScript que acepte una cadena de texto como parámtro.
2. Itera sobre cada carácter de la cadena y aplica las transformaciones descritas anteriormnte.
3. Devuelve la nueva cadena transforada.

### 🔑 Puntos a considerar

- Asegúrate de manejar correctamente los límites del alfabeto. Por ejemplo, la letra 'z' debe convertirse e 'a'
- Mantén los caracteres no alfabéticos sin cabios.

### 📈 Diagrama de flujo


```mermaid
graph TD
    A[Inicio] --> B[Leer cadena de entrada]
    B --> C[Inicializar cadena de salida como vacía]
    C --> D{¿Quedan caracteres por procesar?}
    D -->|No| E[Mostrar cadena de salida]
    E --> F[Fin]
    D -->|Sí| G[Obtener el siguiente carácter]
    G --> H{¿Es una letra?}
    H -->|No| I[Agregar carácter sin cambios a la cadena de salida]
    I --> D
    H -->|Sí| J{¿Es 'z' o 'Z'?}
    J -->|Sí| K[Convertir 'z' a 'a' o 'Z' a 'A']
    K --> L{¿Es una vocal?}
    J -->|No| M[Reemplazar carácter por el siguiente en el alfabeto]
    M --> L
    L -->|Sí| N[Convertir carácter a mayúscula]
    N --> O[Agregar carácter transformado a la cadena de salida]
    L -->|No| O
    O -->D
```


### 🌟 Desafío adicional

Investiga sobre el [**Cifrado César**](https://es.wikipedia.org/wiki/Cifrado_C%C3%A9sar), una técnica de cifrado por sustitución en la que cada letra en el texto es reemplazada por otra letra un número fijo de posiciones más adelante en el alfabeto. ¿Cómo podrías modificar tu función para implementar este tipo de ifrado? 

## 📚 Recursos adicionales

En las siguientes webs puedes encontrar más ejercicios para practicar tus habilidades de programación en JavaScript. Además, en muchos casos se incluyen también las soluciones, por si quieres comparar tu implementación con la propuesta o resolver dudas sobre los ejercicios de este laboratorio:

- 🌐 [W3Schools - JavaScript Exercises](https://www.w3schools.com/js/exercise_js.asp)  
- 🌐 [W3Schools - Más ejercicios de JavaScript](https://www.w3schools.com/JS//js_exercises.asp)  
- 🌐 [W3Resource - JavaScript Exercises](https://www.w3resource.com/javascript-exercises/)