--- 
title: Clase 6 - Maquetacion y Desarrollo Web I 
description-meta: Clase 6
author-meta: Maquetacion y Desarrollo Web I
--- 

# 1. Popups 

Un Popup (ventana emergente), que proviene de la expresión en inglés "Pop Up", que significa "emerger", es como el nombre sugiere, una ventana emergente. Podemos utilizarlas para interactuar con los usuarios de nuestra página de varias maneras.

Los popups se pueden usar para mostrar:

* Notificaciones
* Publicidades
* Mensajes de error o de éxito
* Formularios
* Encuestas

Entre otros.

# 2. Dialog

El elemento `<dialog>` es un tipo especial de pop-up en una pagina web: un pop-up 
que interrumpe el foco del usuario para enfocarse en si mismo.
Hay algunos [casos de uso validos para utilizarlos](https://www.nngroup.com/articles/modal-nonmodal-dialog/), 
pero se debe tomar en consideracion cuando es adecuado hacerlo.

Los dialogs pueden ser de tipo **modal** (solo se puede interactuar 
con el contenido dentro del dialog) o **no-modal** (es posible interactuar 
con el contenido que esta fuera del dialog). 

## 2.1 Modal dialog 

A continuacion se muestra un ejemplo de un modal `<dialog>`.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="zYyNWaw" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/zYyNWaw">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Ahora explicaremos en detalle como se logra esto.
En primer lugar, notemos que tenemos un elemento principal, que es el `<dialog>`
Dentro del dialog tenemos dos `<div>`, uno que es la parte superior que contiene 
el boton para cerrar el pop-up y otro que contiene el contenido propio del pop-up.

```html
<dialog id="dialog" class="dialog">
  <!-- parte superior -->
  <div
       class="flex flex-row items-center justify-end 
              border-b-gray w-full p-1em"
       >
    <button id="closeBtn"
            class="button-close hover:bg-gray cursor-pointer"
            >
      &times;
    </button>
  </div>
  <!-- contenido del popup -->
  <div class="popup-content">
    Gracias por escuchar este album en Spotify!
    <img src="https://i.scdn.co/image/ab67616d0000b273ae6d8e36136353d550b2587d"
         alt="Album"
         style="width: 10em;"
         />
  </div>
</dialog>
```

Luego tenemos un boton con `id="modal"`, que sera el encargado de abrir 
el pop-up.

```html
<button id="openBtn"
        class="button-open"
        >
  Abrir
</button>
```

En la siguiente parte tendremos un tag llamado `<script>`, que sirve para 
insertar JavaScript a nuestra pagina.
JavaScript nos permite agregar interactividad a la pagina web, en este caso,
lo utilizaremos para abrir y cerrar el pop-up.

> Es importante que el tag `script` se encuentre al final del body, para 
que carguen los elementos que vamos a utilizar antes de la ejecucion del mismo.

```js
  // Inicializacion de variables (elementos HTML)
  const dialog = document.getElementById('dialog');
  const closeBtn = document.getElementById('closeBtn');
  const modal = document.getElementById('openBtn');

  // Hacemos que al hacer click en `openBtn` se muestre el modal
  openBtn.addEventListener('click', (event) => {
    dialog.showModal();
  });

  // Hacemos que al hacer click en `closeBtn` se cierre el modal
  closeBtn.addEventListener('click', (event) => {
    dialog.close();
  });
```

Vamos a analizar parte por parte. Primero realizamos una inicializacion de variables 
para obtener los elementos HTML que van a interactuar por `id`. Notese que los 
`id` son los mismos que definimos en HTML con `id="<id-elemento>"`.

Luego hacemos uso de la funcion `addEventListener` que toma como primer parametro 
el nombre del evento (en este caso `click`) y como segundo parametro la funcion que 
se ejecutara cuando ocurra este evento.

Para que se muestre el pop-up en modo modal utilizamos `dialog.showModal()`.

Para que se cierre el pop-up utilizamos `dialog.close()`

> Los eventos son las interacciones que se realizan con los elementos HTML, por ejemplo
el click.

Para aprender mas sobre eventos en JavaScript les recomendamos el [siguiente 
material](https://developer.mozilla.org/es/docs/Learn/JavaScript/Building_blocks/Events).

Con esto ya logramos programar la interactividad de la pagina, utilizando el evento click,
cada vez que clickeemos el boton 'Abrir' se abrira el popup, y al clickear el boton de cerrar, 
se cerrara el mismo.

Como referencia dejamos el CSS utilizado para este ejemplo:
``` css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    padding: 0;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    font-family: sans;
}

.flex {
    display: flex;
}

.flex-row {
    flex-direction: row;
}

.items-center {
    align-items: center;
}

.justify-end {
    justify-content: end;
}

.border-b-gray {
    border-bottom: solid 1px gray;
}

.w-full {
    width: 100%;
}

.p-1em {
    padding: 1em;
}

.hover\:bg-gray:hover {
    color: gray;
}

.cursor-pointer {
    cursor: pointer;
}

.button-open {
    background-color: #2563eb;
    padding: 1em;
    color: white;
    cursor: pointer;
}

.button-open:hover {
    background-color: #1d4ed8;
}

.popup-content {
    padding: 1em;
    display: flex;
    flex-direction: column;
    gap: 0.5em;
    align-items: center;
}

.button-close {
    background: none; 
    font-size: 1.2rem; 
    border: 0;
}

.dialog {
    padding: 0;
    border: solid 1px gray;
    border-radius: 0.5em;
}
```

## 2.2 No-modal dialog 

El dialogo no-modal se diferencia en que no bloquea el resto de la pagina, como 
el modal. Para lograr el efecto solo hay que modificar el JavaScript que 
abre el modal, utilizando la funcion `show()` en lugar de `showModal()`.

```js
  openBtn.addEventListener('click', (event) => {
    dialog.show();
  });
```

# 3. El objeto Window

El objeto Window (Ventana, en español) es un objeto soportado por todos los navegadores en sus versiones más modernas. Representa a la ventana del navegador. Este objeto contiene varios métodos, varios de los cuales usaremos a continuación.

## 3.1 Alert Box

Las alert box (o cajas de alerta, en español), nos permiten asegurarnos de que la información que pongamos en ellas le llegue al usuario. Cuando una Alert Box aparece en pantalla el usuario deberá hacer click en "Ok" para continuar.

#### **Sintaxis**

```js
window.alert("Esto es una alerta!");
```

> **Nota**: si bien se lo menciona para dar un poco de contexto, las definiciones de objeto y método no pertenecen al alcance de este curso. Incluso nos es posible escribir los métodos sin invocar al objeto del que se desprenden, como en el siguiente ejemplo:

#### **Sintaxis**

```js
alert("Esto es una alerta!");
```

**Ambas maneras son igual de validas, asi que de aquí en adelante vamos a seguir con esta segunda sintaxis**

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="WNLRJpG" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/WNLRJpG">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 3.2 Confirm Box

Las confirm box (cajas de confirmación en español) son comúnmente usadas para que el usuario acepte o rechace algo. Cuando una Confirm Box se despliega, nuestro usuario debe clickear "Aceptar" o "Cancelar".

#### **Sintaxis**
```js
confirm("Texto a confirmar");
```

Al seleccionar la opción afirmativa, es retornado un valor True (Verdadero), y cuando se selecciona la opción negativa, es retornado False (Falso), con dichos valores podemos operar luego.

#### **Ejemplo**
```html
<script>
function miFuncion() {
	var texto;
	if (confirm("Presione un botón")) { 
	//esta línea se podría interpretar como if (True)
	texto = "Presionaste Aceptar";
	} else {
	texto = "Presionaste Cancelar";
	}
//Si chequeamos el valor de valor de nuestra variable texto, este seria diferente dependiendo de que haya presionado el usuario
}
</script>
```

> **Nota**: la etiqueta script que se ve en el ejemplo de arriba es una etiqueta de HTML que sirve para que escribamos nuestro código JavaScript dentro, o bien nos sirve para linkear nuestro HTML a  un documento js de forma análoga a como hacemos con nuestros CSS

```html
<script src="script.js"></script> 
```

## 3.3 Prompt Box

Una Prompt Box (la traducción literal no existe, pero podría verse como "Caja de entrada") es utilizada cuando queremos que el usuario ingrese un valor. Tiene 2 parámetros: El mensaje que queremos que el usuario lea, que generalmente le da el contexto sobre lo que se busca introducir, y el texto por defecto que sale en el cuadro de entrada de texto.
Cuando una Prompt Box aparece, el usuario tiene que introducir un valor que se le pide, y después hacer click en "Aceptar" o "Cancelar.

#### **Sintaxis**

```js
prompt("Algún texto","Texto por defecto");
```

Si el usuario da click en "Aceptar", la Prompt Box nos retorna el valor ingresado por el usuario, en cambio, si hizo click en "Cancelar", nos retornara como valor un null (nulo).

#### **Ejemplo**

```js
let persona = prompt("Por favor, introduzca su nombre", "nombre");
let texto;
if (persona == null || persona == "") {
	texto = "El usuario canceló el Prompt";
} else {
	texto = "Hola " + persona + "! ¿Cómo estás hoy?";
}
```

## 3.4 Saltos de línea

Si queremos mostrar saltos de línea dentro de nuestros popus, podemos hacerlo utilizando una barra invertida seguida de una letra n: ```\n```

#### **Ejemplo**

```js
alert("Hola\n¿Cómo estás?");
```

Esto debería mostrar, en dos renglones diferentes:

```
Hola
¿Cómo estás?
```

