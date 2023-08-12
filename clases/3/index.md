--- 
title: Clase 3 - Maquetacion y Desarrollo Web I 
description-meta: Clase 3
author-meta: Maquetacion y Desarrollo Web I
--- 

# 1. Colores
Colorear nuestras páginas es una de las partes más importantes para darles un estilo deseado. Existen muchas formas de especificar los colores en **CSS**, a continuación detallaremos algunas.

## 1.1 Colores Numéricos
se puede determinar un color de varias maneras, una de ellas es mediante el uso de sistemas numéricos, por ejemplo **RGB** o **Hexadecimal**.
>**ejemplo de la propiedad color con notación hexadecimal:**

```css
h1 {
  color: #b71540;
}
```

### 1.1.1 Notación Hexadecimal
La notación hexadecimal asigna valores numéricos a los colores rojo, verde y azul, los 3 colores a partir de los cuales se puede formar el resto. Comúnmente es la más usada.
Los rangos de esta notación van del 0-9 para dichos números, y las letras A-F para los números del 10 al 15. Cuando son usados en secuencias de seis dígitos, se corresponden a dos dígitos por color y se traducen en escala RGB a rangos de entre 0 y 255 para cada uno de los canales, Rojo, Verde y Azul, en ese orden. Combinando distintas secuencias hexadecimales podemos jugar hasta obtener el color que buscamos.
>**ejemplo de colores en hexadecimal:**
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="BapNrPG" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/BapNrPG">
  Learn CSS - HEX colors</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 1.2 Colores nombrados
Existen una serie de colores que ya vienen establecidos, son nombrados con palabras clave que corresponden al nombre de dicho color en inglés. Algunos de los más usados podrían ser **black** (negro), **white** (blanco), etc.
>**ejemplo de la propiedad color con una palabra clave de color ya definida:**
```css
h1 {
  color: black;
}
```

## 1.3 Transparencia
Adicionalmente se pueden definir dos dígitos más, conocidos como "alpha", que es básicamente el porcentaje de transparencia de nuestro color.
>**ejemplo de transparencia:**
por ejemplo si quisieramos un color negro, nuestro codigo hexadecimal seria: #000000
El mismo color pero con 0% de transparencia sería: #00000000, en cambio para un 50% sería: #00000080
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="VwPLXdr" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/VwPLXdr">
  Learn CSS - HEX Codes With Alpha</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Así como los colores vistos antes, otra palabra clave existente es **transparent** (transparente), que representa a un color totalmente transparente
**De igual forma, siempre es recomendable definir nuestros propios colores de forma más precisa con la notación Hexadecimal**

## 1.4 Palabras clave del sistema
Son palabras clave de colores que vienen definidas a partir del tema de nuestro sistema operativo. Por ejemplo **Background**, el cual corresponde al color del fondo de pantalla del escritorio, como esta hay muchas más. Dichas palabras clave al depender del sistema cambian según el contexto donde son usadas. siempre van a empezar por mayúscula para diferenciarse de las otras palabras clave de colores estándar.

## 1.5 ¿Dónde usar color en CSS?
Si una propiedad CSS acepta el tipo de datos `<color>` como uno de sus valores, va aceptar cualquiera de los métodos de coloración. Para darle estilo al texto, existen `color` (color del texto), `text-shadow` (color de la sombra del texto) y `text-decoration-color` (color del subrayado), entre otras. Todas son propiedades que aceptan colores como sus valores, o como parte de sus valores.

Para los fondos, se puede especificar un color como valor para `background` (color de fondo, no confundir con la palabra clave **Background** que vimos antes)

Por último, `border-color` (color del borde) y `outline-color` (color del outline), sirven para darle color a nuestras boxes (tema que veremos más adelante en esta misma unidad).

# 2. Unidades de dimensionamiento
En este módulo aprenderemos a dimensionar elementos mediante CSS, trabajando con el medio flexible de la web.

La web es un medio responsivo, pero a veces deseamos controlar sus dimensiones para mejorar la calidad general de la interfaz. Un buen ejemplo de esto es limitar la longitud de las líneas para mejorar la legibilidad.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="bGgEGxj" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/bGgEGxj">
  Learn CSS - Units - Intro</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Para este caso, puede usar una unidad ch, que es igual al ancho de un carácter "0" en la fuente renderizada a su tamaño calculado. Esta unidad le permite limitar el ancho del texto con una unidad diseñada para ajustar su tamaño, lo que a su vez, permite un control predecible independientemente del tamaño de ese texto. La unidad ch es una de las pocas unidades que son útiles para contextos específicos como este ejemplo.

## 2.1 Porcentajes

Al usar un porcentaje en CSS, necesita saber cómo se calcula éste. Por ejemplo, width se calcula como un porcentaje del ancho del elemento principal.

```
div {
  width: 300px;
  height: 100px;
}

div p {
  width: 50%; /* calculated: 150px */
}
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ZELbwwj" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/ZELbwwj">
  Learn CSS - Sizing - Percentages</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

En el fragmento anterior, tanto margin-top como padding-left se calcularán en 150px.

## 2.2 Dimensiones y longitudes

Si adjunta una unidad a un número, se convierte en una dimensión. Por ejemplo, 1rem es una dimensión.

Las longitudes son dimensiones que se refieren a la distancia y pueden ser absolutas o relativas.

### Longitudes absolutas

Todas las longitudes absolutas se resuelven contra la misma base, lo que las hace predecibles dondequiera que se utilicen en su CSS. Por ejemplo, si usa cm para dimensionar su elemento y luego imprime, debería ser exacto si lo compara con una regla.

Las longitudes absolutas pueden resultar útiles a la hora de imprimir.

                    
|Unidad |Nombre |Equivalente a|
| :------------ |:---------------:| -----:|
|cm |Centímetros |1 cm = 96 px/2.54|
|mm |Milimetros |1 mm = 1/10 de 1 cm|
|Q |Cuarto de milímetro |1Q = 1/40 de 1 cm|
|in |Pulgadas |1 in = 2.54 cm = 96 px|
|pc |Picas |1pc = 1/6 de 1 in|
|pt |Puntos |1 pt = 1/72 de 1 in|
|px |Pixeles |1 px = 1/96 de 1 in|
                

### Longitudes relativas

La longitud relativa se calcula contra un valor base, muy parecido a un porcentaje. La diferencia entre estos y los porcentajes es que puede dimensionar los elementos contextualmente

|Unidad |Equivalente a|
| :------------ |:----------------:|
|em|En relación con el tamaño de fuente, es decir, 1.5em será un 50% más grande que el tamaño de fuente calculado base de su padre. (Históricamente, la altura de la letra mayúscula "M").|
|ex|Heurística para determinar si se debe usar la x-height,, una letra "x" o `.5em` en el tamaño de fuente calculado actual del elemento.|
|cap|Altura de las letras mayúsculas en el tamaño de fuente calculado actual del elemento.|
|ch|Avance de carácter promedio de un glifo estrecho en la fuente del elemento (representado por el glifo "0").|
|ic|Avance de carácter promedio de un glifo de ancho completo en la fuente del elemento, representado por el glifo "水" (ideograma de agua CJK, U + 6C34).|
|rem|Tamaño de fuente del elemento raíz (el valor predeterminado es 16px).|
|lh|Altura de línea del elemento.|
|rlh|Altura de línea del elemento raíz.|

<img src="https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/ttaikDgwEC572lrGgWlG.svg"/>

### Longitudes relativas

Puede utilizar las dimensiones de la ventana gráfica (ventana del navegador) como una base relativa. Estas unidades reparten el espacio disponible de la ventana gráfica.

|unidad|relativa a|
| :------------ |:----------------:|
|vw|1% del ancho de la ventana gráfica. Se usa esta unidad para hacer trucos de fuentes geniales, como cambiar el tamaño de una fuente de encabezado en función del ancho de la página, de modo que a medida que el usuario cambia el tamaño de la ventana, la fuente también cambia de tamaño.|
|vh|1% de la altura de la ventana gráfica. Puede usarla para organizar elementos en una interfaz de usuario, si tiene una barra de herramientas de pie de página, por ejemplo.|
|vi|1% del tamaño de la ventana gráfica en el eje en línea del elemento raíz. El eje se refiere a los modos de escritura. En los modos de escritura horizontal como el inglés, el eje en línea es horizontal. En los modos de escritura vertical como algunos tipos de letra japoneses, el eje en línea va de arriba a abajo|
|vb|1% del tamaño de la ventana gráfica en el eje del bloque del elemento raíz. Para el eje del bloque, esta sería la direccionalidad del lenguaje. Los idiomas LTR como el inglés tendrían un eje de bloque vertical, ya que los lectores en inglés analizan la página de arriba a abajo. Un modo de escritura vertical tiene un eje de bloque horizontal|
|vmin|1% de la dimensión más pequeña de la ventana gráfica.|
|vmax|1% de la dimensión más grande de la ventana gráfica.|

```
div {
  width: 10vw;
}

p {
  max-width: 60ch;
}
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="JjEYqXa" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/JjEYqXa">
  Learn CSS - Sizing - Relative Units </a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

En este ejemplo, el div será el 10% del ancho de la ventana gráfica, porque 1vw es el 1% del ancho de la ventana gráfica. El elemento p tiene un max-width de 60ch que significa que no puede exceder el ancho de 60 caracteres "0" en la fuente y el tamaño calculados.


# 3. Flexbox

## 3.1 La propiedad display
La propiedad `display` sirve para dos cosas.  
Una de ellas es determinar si la caja (box) a la que se aplica actua como inline o como bloque. 

```css
.mi-elemento {
    display: inline;
}
```

Los elementos **inline** se comportan como palabras en una oración. Se ponen uno al lado del otro en la misma linea. Los elementos como `<span>` y `<strong>`, que son tipicamente usados para darle estilo a partes del texto dentro de un elemento padre como un `<p>` (párrafo), son inline por defecto. También preservan los espacios en blanco.

![](https://web-dev.imgix.net/image/VbAJIREinuYvovrBzzvEyZOpw5w1/GezxDZXkJgkMevkKg39M.png?auto=format&w=845)

> No se puede setear un ancho o alto (width, height) explicito a los elementos inline. Cualquier margin o padding que se le agregue va a ser ignorado.

```css
.mi-elemento {
    display: block;
}
```
Los elementos `block` no se ponen uno al lado del otro. Se crean en una nueva línea.  
A menos que se modifique por CSS, un elemento block se va a expandir al ancho de la dimensión inline, es decir, todo el ancho de la página. 

 ```css
.mi-elemento {
    display: flex;
}
```
La propiedad `display` también determina cómo se comportan los elementos hijos del elemento. Por ejemplo, si usamos la `display: flex` la caja se transforma en una caja a nivel de bloque, y sus hijos en items flex. Lo que permite controlar su alineación, orden y flujo.

## 3.2 Flexbox en detalle
Flexbox es un mecanismo de layout para layouts unidimensionales. Es decir, a lo largo de un solo eje, horizontal o vertical. Por defecto, flexbox alinea los elementos hijos uno al lado del otro, en la dirección inline y los estira (stretch) en la dirección block, para que tengan la misma altura.

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="html,result" data-slug-hash="GRwbGQY" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/GRwbGQY">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 3.2.1 Dirección de los items
Para cambiar la dirección en la que se muestran los elementos hijos de un contenedor con `display: flex;` se utiliza la propiedad `flex-direction`.
Puede tener los siguientes valores:

* row: los items se muestran en fila (horizontal).
* column: los items se muestran en una columna (vertical)
* row-reverse: los items se muestran en fila con el orden inverso.
* column-reverse: los items se muestran en columna con el orden inverso.

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="html,result" data-slug-hash="RwqzJBY" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/RwqzJBY">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

### 3.2.2 Alineamiento de los items
Hay dos tipos de propiedades flex para alineamiento, unas orientadas a la distribución del espacio y otras al alineamiento. Las propiedades para distribuir el espacio son:

`justify-content`: distribuye el espacio en el eje principal.
`align-content`: distribuye el espacio en el eje secundario.

Las propiedades para alinear son:
`align-self`: alinea un único elemento en el eje secundario.
`align-items`: alinea todos los items en el eje secundario.

Si estás trabajando en el eje principal las propiedades empiezan con `justify-`. Las del eje secundario empiezan con `align-`

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="html,result" data-slug-hash="bGgwLgz" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/bGgwLgz">
  Learn CSS - Flexbox - Justify content</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="html,result" data-slug-hash="poREawo" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/poREawo">
  Learn CSS - Flexbox - Align content</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

# 4. Maquetacion de header y footer.

Ahora veremos una pequeña guía sobre la maquetación de un header y un footer básico utilizando HTML y CSS.

## 4.1 Primer paso: Estructura de un Documento HTML

Pueden usar el que entregaron la clase pasada, o pueden crear uno nuevo. Les recordamos que esta es la estructura basica:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Título de la Página</title>
    <!-- Enlaces a archivos CSS y más metadatos van aquí -->
</head>
<body>
    <!-- Contenido de la página -->
</body>
</html>
```
## 4.2 Segundo paso: Creación del Header

Creamos un elemento ``<header>`` en el ``<body>`` de la página, algunas de las etiquetas que decidimos usar son ``<nav>``, ``<ul>``, ``<li>``.
Ejemplo de código HTML para el header:

```html
<header>
    <div class="logo">Header</div>
    <nav>
        <ul>
            <li>Home</a></li>
            <li>About</a></li>
            <li>Services</a></li>
            <li>Contact</a></li>
        </ul>
    </nav>
</header>
```

## 4.3 Tercer paso: Creación del Footer

Creamos un elemento `<footer>` en el `<body>` de la página, para este ejemplo solo usaremos un `<p>`

```html
<footer>
    <p>&copy; 2023 Mi Sitio Web. Todos los derechos reservados.</p>
</footer>
```

## 4.4 Cuarto paso: Estilización

Lo primero que tenemos que hacer, es crear nuestro archivo de estilos `style.css` en la misma carpeta donde tenemos nuestro `index.html`

### 4.5 Como vincular un archivo de estilos, con un documento HTML

Una vez tengamos nuestro archivo `style.css` creado, deberemos referenciarlo desde  `index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Título de tu Página</title>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
    <!-- Contenido de la página -->
</body>
</html>
```

`<link>`: Es un elemento HTML que se utiliza para vincular recursos externos al documento.
rel="stylesheet": Indica que el recurso es una hoja de estilo.
type="text/css": Especifica el tipo de recurso que se vinculará.
href="style.css": Es el atributo que contiene la ruta al archivo style.css

### 4.6 Ejemplo final con CSS y HTML 

<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="html,result" data-slug-hash="ZEmdjYK" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/ZEmdjYK">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
