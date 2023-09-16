--- 
title: Clase 7 - Maquetacion y Desarrollo Web I 
description-meta: Clase 7
author-meta: Maquetacion y Desarrollo Web I
--- 

# 1. Formularios

La mayoria de los sitios web incluyen de una u otra manera a los formularios. Los mismos permiten a nuestros usuarios interactuar con nuestra página, validar la informacion que ingresaron, y enviar los datos a un servidor.
En esta clase nos centraremos unicamente en lo que podemos hacer con HTML, sin necesidad de CSS o JavaScript, sin embargo, cabe mencionar que existe la posibilidad de desactivar estas validaciones HTML seteando el atributo ```novalidate``` en nuestro ```<form>```, si lo que quisieramos es procesar los datos despues usando JavaScript, no es nuestro caso, pero existe la posibilidad de hacerlo.

## 1.1 El elemento form

El elemento html ```<form>``` es quien nos permite lograr esto, dentro de el encontramos todos los controles, sean interactivos o no, que componen a nuestros formularios.

## 1.2 Enviando un formulario

Los formularios son enviados cuando el usuario activa un **botón de enviar**, que se encuentra dentro del ```<form>```.
Para estos podemos usar tanto ```<input>``` como ```<button>```.
Usando ```<input>```, el contenido del atributo ```value``` será el texto que se muestre en el botón. En cambio, si usamos ```<button>```, el texto que se mostrará es el que escribamos entre las etiquetas de ```<button>```

#### Ejemplo

```html
<input type="submit" value="Enviar Formulario 1">
<button type="submit">Enviar Formulario 2</button>
```

**Resultado**

<input type="submit" value="Enviar Formulario 1">
<button type="submit">Enviar Formulario 2</button>

## 1.3 Request HTTP

Para un formulario simple, todo lo que necesitamos es nuestro  elemento ```<form>``` y un par de entradas en su interior, junto con un botón de enviar. Sin embargo, hay mucho mas que podemos hacer mas alla de esto.
Los atributos de nuestro ```<form>``` setean **Requests de HTTP** (**HyperText Transfer Protocol**, protocolo de comunicación que permite las transferencias de información a través de archivos (**HTML**… entre otros), y es mediante estos requests que los datos ingresados en nuestro formulario son enviados, por ejemplo, hacia otra página. Dichos atributos a los que nos referimos son ```action``` y ```method```.
El primero, ```action```, define la URL que procesa los datos del formulario. De no modificarlo, por defecto los datos del formulario son enviados dentro de la misma página en la que nos encontramos.
El segundo, ```method```, define cual es el metodo HTTP utilizado por el Request para enviar dichos datos. Generalmente se utilizan ```GET``` y ```POST```.
Con ```GET``` los datos son enviados como Strings con un formato ```name=value```, los cuales son concatenados a la URL definida por ```action```.
En cambio, con ```POST``` los datos se envian con el cuerpo de nuestro request HTTP. Cuando enviamos datos que requieren de cierta seguridad, como contraseñas, **siempre debemos usar** ```POST```.
Existen otros metodos HTTP, pero para el contexto y alcance de este curso no serán necesarios.

## 1.4 Despues de enviar nuestro formulario

Cuando el usuario completa el formulario y lo envia, los nombres y valores de los campos relevantes de dicho formulario son enviados en un formato de pares nombre/valor.
Estos campos relevanters son todos los que posean un atributo ```name```, cuyo valor sera el nombre del par. El valor del par, en cambio, dependerá de donde provengan los datos: puede ser tanto el contenido de un atributo ```value```, o un valor que haya ingresado el usuario, o un valor que haya elegido el mismo dentro de una serie de opciones.
Tomemos este ultimo caso como ejemplo:

#### Ejemplo

```html
<form method="GET">
	<label for="jugador">Elegí un jugador:</label>
	<select name="jugador" id="jugador">
		<option value="messi">Lionel Messi</option>
		<option>Ronaldinho Gaucho</option>
		<option value="cristiano">Cristiano Ronaldo</option>
	</select>
	<input type="submit" value="Enviar">
</form>
```

**Resultado**

<form method="GET">
	<label for="jugador">Elegí un jugador:</label>
	<select name="jugador" id="jugador">
		<option value="messi">Lionel Messi</option>
		<option>Ronaldinho Gaucho</option>
		<option value="cristiano">Cristiano Ronaldo</option>
	</select>
	<input type="submit" value="Enviar">
</form>

En este caso, el valor de un ```<select>``` será el atributo ```value``` del ```<option>``` elegido por el usuario, o, como se ve en el caso del segundo ```<option>```, el de Ronaldinho, el cual no posee dicho atributo, el valor será el texto que contiene ```<option>``` adentro.
Elegir "Lionel Messi" (o no elegir nada, ya que por defecto se elije la primer opcion mostrada si no se selecciona ninguna otra), y hacer click en el botón de enviar va a provocar que se recargue la página seteando la URL como:

```
https://url.de.tu.pagina?jugador=messi
```

En el caso de Elegir "Ronaldinho Gaucho", dado que como mencionamos antes dicho ```<option>``` no posee ```value```, nuestra URL se seteara como:

```
https://url.de.tu.pagina?jugador=Ronaldinho+Gaucho
```

Una vez enviado el formulario, la informacion enviada incluye, como ya se menciono, todos los nombres y valores de todos los datos relevantes que posean un ```name```, excepto los checkboxes no seleccionados, los bottones radio no seleccionados, y los nombres y valores de cualquier otro botón que no sea el que envió dicho formulario. Para el resto de campos relevantes, si poseen ```name``` pero ningun valor fue ingresado o está ahi por defecto, dicho ```name``` es enviado con valor vacio.

## 1.5 Algunas buenas practicas y cosas a tener en cuenta

Existen en total 22 tipos de entradas, no vamos a verlos todos, pero cabe resaltar que incluir un valor es opcional, y usualmente, **una mala idea**, cuando lo que buscamos es que el ususario ingrese información.
Sin embargo, como vimos arriba, para los elementos ```<input>```, en los cuales el usuario no puede editar los valores, **siempre deberiamos incluirlos nosotros**.
Esto tambien aplica a otras entradas como: ```hidden```, ```radio```, ```checkbox```, ```submit```, ```button``` y ```reset```.
Usar ```name``` unicos para cada dato relevante hace que el procesamiento del lado del servidor sea mas simple, y es recomendable hacerlo, con las ```checkbox``` y los botones ```radio``` siendo las excepciones a esta regla.

### 1.5.1 Radio Buttons

Para los botones de tipo radio, esto se debe a que dentro de un grupo de botones radio, todos deben tener el mismo atributo ```name``` para que se cree el efecto de que solo uno puede ser elegido a la vez. En este caso, el ```name``` unico pertenecerá a todo el grupo de botones radio y su funcion será distinguir a dicho grupo de otros grupos de botones que podamos tener. Lo que si debemos tener en cuenta es de que cada botón de nuestro grupo posea un ```value``` unico que lo diferencie de los demas del grupo. Solo el valor del atributo ```value``` del botón seleccionado es enviado con nuestro request.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjBQJEv" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/JjBQJEv">
  Radio controls</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 1.5.2 Checkboxes

Es una opcion valida tener checkboxes pertenecientes a un mismo grupo teniendo el mismo ```name```. Solamente las checkbox seleccionadas van a enviar su ```name``` y su ```value``` con el formulario. Si tenemos varias seleccionadas y todas tienen el mismo nombre, dicho nombre va a ser enviado con (esperemos) valores distintos. Si tenemos diferentes entradas relevantes con un mismo nombre, incluso si no todas son checkboxes, **todas** van a ser enviadas, separadas por ```&```.
Si no le incluimos un ```value``` a un checkbox, el valor del checkbox seleccionado por defecto es ```on```, lo que probablemente no nos sea muy util.

#### Ejemplo

Con 3 checkboxes, todas llamadas ```chk``` y todas seleccionadas, obtendriamos algo como esto:

```html
https://url.de.tu.pagina?chk=on&chk=on&chk=on
```

No muy entendible que digamos, ni siquiera podemos diferenciar cual checkbox es cual.
Para volver un checkbox requerido, le podemos agregar el atributo ```required```. Siempre debemos informarle al usuario cuando un checkbox debe ser marcado, o cuando cualquier otro campo es requerido. Tener en cuenta que ```required``` solo vuelve requerida a la checkbox a la que lo agregamos, pero no influye al resto con el mismo nombre.

## 1.6 Labels y Fieldsets

Para que nuestros usuarios sepan como llenar un formulario, dicho formulario debe ser accesible. Cada estructura relevante edbe tener una etiqueta, tambien queremos que los grupos de elementos las tengan.
Para entradas individuales usamos ```<label>```, mientras que para los grupos sus elementos son etiquetados con el contenido del ```<legend>``` perteneciente al ```<fieldset>``` que los agrupa.

### 1.6.1 Label

Si volvemos a ver los ejemplos anteriores, vamos a ver que todos los inputs de datos tenian su ```<label>```, exceptuando los botones de enviar. ```<label>``` nos permite etiquetar las estructuras de nuestro ```<form>``` con nombres accesibles. Para los botones de enviar, su nombre accesible proviene de su contenido o valor, segun el caso de boton, para todo el resto de tipos de entrada en nuestro formulario, todos requiren tener su ```<label>```.
Si no etiquetamos nuestras entradas, el buscador va a mostrarlas de igual forma, pero el usuario no va a saber que debe ingresar o hacer con ellas.
Para asociar explicitamente una estructura con un ```<label>``` debemos incluir el atributo ```for``` en la etiqueta con su valor siendo el ```id``` de la estructura con la que la estamos asociando.

#### Ejemplo

```html
<label for="nombre_completo">Ingresa tu nombre</label>
<input type="text" id="nombre_completo" name="nombre">
```

**Resultado**

<label for="nombre_completo">Ingresa tu nombre</label><input type="text" id="nombre_completo" name="nombre">

No es recomendable agregar elementos interactivos en nuestras etiquetas, ya que eso podria confundir a los usuarios.
Generalmente se acostumbra a colocar los ```<label>``` antes de la estructura correspondiente, excepto en los casos de los botones radio y los checkboxes. No es obligatorio hacerlo, pero es algo que ya esta bastante extendido.

### 1.6.2 Fieldset

Etiquetar nos provee el nombre reconocible para el elemento con el cual esta asociada la etiqueta.
En los grupos de elementos es necesario etiquetar a cada uno de los miembros del grupo, y ademas, al grupo en si.
Para etiquetar al grupo, agrupamos todos sus elementos dentro de un ```<fieldset>```, el cual tendra un ```<legend>``` encargado de asignarle la etiqueta.

#### Ejemplo

```html
<fieldset>
<legend>Who is your favorite student?</legend>
	<ul>
		<li>
			<label>
				<input type="radio" value="blendan" name="machine"> Blendan Smooth
			</label>
		</li>
		<li>
			<label>
				<input type="radio" value="hoover" name="machine"> Hoover Sukhdeep
			</label>
		</li>
		<li>
			<label>
				<input type="radio" value="toasty" name="machine"> Toasty McToastface
			</label>
		</li>
	</ul>
</fieldset>
```

**Resultado**

<fieldset>
<legend>Who is your favorite student?</legend>
	<ul>
		<li>
			<label>
				<input type="radio" value="blendan" name="machine"> Blendan Smooth
			</label>
		</li>
		<li>
			<label>
				<input type="radio" value="hoover" name="machine"> Hoover Sukhdeep
			</label>
		</li>
		<li>
			<label>
				<input type="radio" value="toasty" name="machine"> Toasty McToastface
			</label>
		</li>
	</ul>
</fieldset>

En este ejemplo, los ```<label>``` implicitos cada uno etiqueta a un boton radio y ```<legend>``` etiqueta al grupo de botones radio.
Anidar un ```fieldset``` dentro de otro ```fieldset``` es una practica estandar, por ejemplo, si buscaramos dividir un formulario con preguntas en varios grupos de preguntas distintos segun el tema, podriamos tener un ```fieldset``` cuyo ```legend``` sea "Preguntas sobre futbol" y despues otro ``fieldset``` adentro cuyo ```legend``` fuera "¿Quien es tu jugador favorito?"

```html
<fieldset>
<legend>Preguntas sobre futbol:</legend>
	<ul>
		<li>
			<fieldset>
			<legend>¿Quien es tu jugador favorito?</legend>
				<ul>
					<li>
            <!-- resto del codigo -->
```

<fieldset>
<legend>Preguntas sobre futbol:</legend>
	<ul>
		<li>
			<fieldset>
			<legend>¿Quien es tu jugador favorito?</legend>
				<ul>
					<li>
					</li>
				</ul>
			</fieldset>
		</li>
	</ul>
</fieldset>

Cabe destacar que tanto ```<legend>``` como ```<fieldset>``` pueden ser estilados con el uso de CSS

## 1.7 Tipos de entradas y teclado dinamico

Como mencionamos, hay 22 tipos distintos de entradas de datos. En ciertos casos, si el usuario esta en un dispositivo como un celular, el teclado solo aparece cuando es necesario, por ejemplo, cuando el usuario toca la casilla "Usuario" y el teclado aparece para permitirle escribir en dicho campo.
Para estos casos, el tipo de entrada determina el tipo de teclado mostrado, y es algo que podemos optimizar.
Por ejemplo, un ```<input type="tel">``` muestra el teclado optimizado para ingresar un numero telefonico, mostrando unicamente numeros y caracteres relacionados, en cambio ```type =email``` incluye tanto el ```@``` como ```.```, etc.
El teclado que se despliegue, ademas de segun el tipo de entrada, tambien variara segun el dispositivo, el ejemplo mas sencillo es que no es igual en Android o en iPhone.

# 2. Ejemplo: Formulario de Login

Ya vistos los conceptos sobre formularios, pasaremos al ejemplo practico de un formulario de Login (inicio de sesion). En este formulario el usuario debera ingresar su email y su contraseña para ingresar a un determinado sitio web.

La estructura HTML de un formulario de login es:

```html
<form>
	<label for="email">Ingrese su email:</label>
	<input id="email" type="email" placeholder="Email" />
	<label for="password">Ingrese su contraseña:</label>
	<input id="password" type="password"
       	placeholder="Contraseña"
	/>
  <button type="submit">
  	Login
  </button>
</form>
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWZKbRr" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/MWZKbRr">
  Login</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Ahora empezamos a agregar CSS. En primer lugar, haremos una clase `login-form` para nuestro elemento `form`.

```css
.login-form {
  display: flex;
  flex-direction: column;
  width: 20em;
  gap: 0.5em;
  font-family: sans-serif;
  border: solid 1px #d4d4d4;
  padding: 2.5em;
  border-radius: 0.5em;
  box-shadow: #e5e5e5 0px 1px 4px;
}
```

Es un contenedor con display flex, en dirección column. Le pusimos un ancho determinado y aprovechamos para elegir el font-family (que se aplicará a todos los elementos del contenedor). También agregamos border-radius (para redondear bordes) y le pusimos box-shadow para que tenga sombra en los bordes.

Pueden encontrar efectos de sombra en [esta página](https://getcssscan.com/css-box-shadow-examples).

Ahora vamos con los `label`.

```css
.login-label {
  color: #292524;
  font-size: 0.8rem;
  margin-top: 0.5em;
}
```

En este caso le pusimos un color de texto diferente y le asignamos un tamaño menor al resto del texto. También le agregamos un `margin-top` para que estén un poco más separados entre sí.

En cuanto a los estilos de los inputs hicimos lo siguiente:

```css
.login-input {
  padding: 0.75em;
  border-radius: 0.25em;
  border: solid 1px #d4d4d4;
}
```

Es decir, un poco de padding, border-radius y un borde de color gris. 

Finalmente, para el boton de login:

```css
.login-button {
  margin-top: 1em;
  padding: 0.6em 0.5em;
  border-radius: 0.5em;
  border: none;
  background-color: #2563eb;
  color: #eff6ff;
  font-weight: 600;
  transition: ease-in-out 0.2s;
}

.login-button:hover {
  background-color: #3b82f6;
  cursor: pointer;
}
```

Agregamos padding (distinto en vertical que en horizontal), `margin-top` para que se aleje más del resto del formulario. Le quitamos el borde, agregamos un color de fondo y una transición para cuando se haga hover sobre el mismo se vea un efecto de cambio de color de fondo.

A continuación el resultado final:

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ZEVXzJe" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/ZEVXzJe">
  Login with styles</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

