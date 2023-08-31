--- 
title: Clase 5 - Maquetacion y Desarrollo Web I 
description-meta: Clase 5
author-meta: Maquetacion y Desarrollo Web I
--- 
# 1. Slideshow

Un slideshow o slider, también conocido como carrusel se refiere a un grupo de elementos en fila sobre los que se puede navegar, como una especie de diapositiva.

## 1.1 Slider básico

Podemos crear un slider utilizando la siguiente estructura HTML.

```html
<div class="slider">
  <div class="slide" id="slide-1">1</div>
  <div class="slide" id="slide-2">2</div>
  <div class="slide" id="slide-3">3</div>
  <div class="slide" id="slide-4">4</div>
  <div class="slide" id="slide-5">5</div>
</div>
```

Ahora con css vamos a hacer que se pongan en fila y que se puedan scrollear.

```css
/* clase del contenedor principal */
.slider {
  width: 20em;
  height: 20em;
  display: flex;
  overflow-x: auto;
}

/* clase para cada slide individual*/
.slide {
  width: 20em;
  flex-shrink: 0;
  height: 100%;
}
```

Con esto ya cumplimos dicho requerimiento.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="wvRWJqy" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/wvRWJqy">
  Untitled</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 1.2 Links de navegación

Ahora si queremos agregar links para navegar entre slides, necesitamos incorporar elementos `<a>` que pongan foco en cada elemento.

```html
<div class="slide-wrap">
 
  <a href="#slide-1">1</a>
  <a href="#slide-2">2</a>
  <a href="#slide-3">3</a>
  <a href="#slide-4">4</a>
  <a href="#slide-5">5</a>

  <div class="slider">
	<div class="slide" id="slide-1">1</div>
	<div class="slide" id="slide-2">2</div>
	<div class="slide" id="slide-3">3</div>
	<div class="slide" id="slide-4">4</div>
	<div class="slide" id="slide-5">5</div>
  </div>

</div>
```

Ahora que tenemos esto listo, vamos a darle un poco de estilo a los botones para que nos quede una mejor presentación.

```css
/* clase para el contenedor padre */
.slide-wrap {
  display: flex;
  flex-direction: column;
  justify-items: center;
  align-items: center;
  gap: 0.5em;
}

.slider {
  width: 20em;
  height: 20em;
  display: flex;
  overflow-x: auto;
}

/* clase para cada slide individual */
.slide {
  width: 100%;
  flex-shrink: 0;
  height: 100%;
 
  /* estilos de ejemplo */
  background: gray;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2rem;
}



/* clase para el elemento que encierra los links de navegación */
.slide-nav {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  border-radius: 20em;
  font-weight: bold;
  gap: 0.5em;
}

/* estilo de los  links de navegación */
.slide-nav > a {
  color: black;
  text-decoration: none;
  width: 1.5rem;
  height: 1.5rem;
  background: white;
  border: solid 1px #d4d4d4;
  border-radius: 20em;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.25em;
  font-size: 0.8rem;
}

.slide-nav > a:hover {
  background-color: #f5f5f5;
}

body {
  font-family: sans;
  background-color: #fafafa;
}
```

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="ZEVOePz" data-editable="true" data-user="Ignacio-Martin-Citate-G-mez" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Ignacio-Martin-Citate-G-mez/pen/ZEVOePz">
  Slider con navegacion</a> by Ignacio Martin Citate Gómez (<a href="https://codepen.io/Ignacio-Martin-Citate-G-mez">@Ignacio-Martin-Citate-G-mez</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

# 2. Transiciones
Cuando interactuamos con una página web podemos observar que ciertos elementos poseen ciertos estados. Por ejemplo, los botones pueden cambiar de color cuando el mouse les pasa por encima (el evento hoover, que ya vimos en la clase anterior)
Las transiciones se ocupan del cambio entre ambos estados del elemento un elemento, definen como sera el comportamiento de dicho cambio, si será gradual, si tardará mas o menos tiempo, si se producira al instante o con un retraso, etc.

## 2.1 Lo básico
Por defecto, CSS cambia el estilo de los estados de forma instantanea, es decir, no hay transición en el medio.
Haciendo uso de las transiciones, podemos interporlar entre ambos estados del elemento, el inicial y el objetivo, brindandole al usuario de nuestra página una mejor experiencia visual al momento del uso.

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="zYzNrJV" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/zYzNrJV">
  Learn CSS: Transitions - instant vs transitioned (no button)</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

Para utilizar transiciones en nuestro CSS hay varias propiedades que podemos modificar. A continuación veremos algunas.

## 2.2 Propiedades de una Transición
Con ``transition-property`` especificamos que estilo/s van a realizar la transición. Acepta como parametros a una o mas propiedades CSS separadas por comas.

#### ejemplo de sintaxis
```css
.mi-elemento {
  transition-property: background-color;
}
```

#### ejemplo en funcionamiento
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="VwWPeEj" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/VwWPeEj">
  Learn CSS: Transitions - transition-property</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2.3 Duración una transición
La propiedad ``transition-duration`` es usada para definir el tiempo que tarada una transición en completarse.
Acepta como parametro **unidades de tiempo**, ya sea en segundos (s) o milisegundos (ms). Por defecto siempre es **0s** (transición instantea)

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="wvegMYp" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/wvegMYp">
  Learn CSS: Transitions - transition-duration</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2.4 Retraso de una transición
Con ``transition-delay`` especificamos el tiempo que nuestra transición tardara en empezar a producirse. Si no lo especificamos, las transiciónes comienzan de forma instantea ya que el valor por defecto es **0s**. Esta propiedad acepta los mismos parametros que la anterior, **unidades de tiempo**.

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="jOwyWep" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/jOwyWep">
  Learn CSS: Transitions - transition-delay</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
Esto puede servirnos para escalonar / encadenar transiciones, efecto que podriamos lograr estableciendo diferentes tiempos de retraso para cada transición, con cada trasición posterior teniendo un tiempo de retraso mayor a la anterior.

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="yLXgeRQ" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/yLXgeRQ">
  Learn CSS: Transitions - transition-delay staggered</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2.5 Un atajo útil
Como la mayoria de las propiedades de CSS, hay una version acortada, o un "atajo".
En este caso es ``transition``, que agrupa a ``transition-property``, ``transition-duration`` y ``transition-delay``, entre otras.

#### ejemplo de sintaxis

```css
.version-larga {
  transition-property: transform;
  transition-duration: 300ms;
  transition-delay: 0s;
}

.version-corta {
  transition: transform 300ms 0s;
}
```

## 2.6 Transformaciones
La propiedad ``transform`` nos permite escalar, rotar o transladar un elemento de forma arbitraria, y nos permite obtener animaciones mas suaves y atractivas a la vista.

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="GRErowE" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/GRErowE">
  Learn CSS: Transitions - transform</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2.7 Colores
Antes, durante y despues de una interacción, el color tambien puede servirnos como indicador del estado de nuestro elemento.
El ejemplo mas simple es un boton que cambia de color con un evento **hoover**, esto es muy util para darle feedback al usuario.
Las propiedades ``color``, ``background-color`` y ``border-color`` son solo algunas de las propiedades donde el color puede ser transicionado en una interacción.

## 2.8 Sombras
Usualmente se las transiciona para producir un cambio en la elevación, indicando, por ejemplo, el focus del usuario.

#### ejemplo
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gORgPQx" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/gORgPQx">
  Learn CSS: Transitions - shadow (elevation)</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 2.9 Triggers de transición
Como ya mencionamos, nuestro CSS debe incluir un cambio de estado y un evento que dispare (trigger) dicho cambio para que nuestra transición se active. El ejemplo mas sencillo es el que mencionamos anteriormente, ``:hover``, que se dispara cuando el usuario pone el mouse encima del elemento.

#### algunos ejemplos mas

``:hover`` --> se activa si el cursor esta sobre el elemento. (por ejemplo: nuestro mouse pasa por sobre un boton)

``:focus`` --> se activa si el elemento se encuentra en foco. (ejemplo: un interruptor es presionado y queda en foco)

``:active`` --> se activa cuando el elemento es, valga la redundancia, activado. (por ejemplo: un boton esta siendo presionado por el usuario)

## 2.10 Consideraciones sobre el rendimiento de nuestra página
A veces cuando trabajamos con transiciones de CSS podemos llegar a ver problemas de rendimiento con ciertas propiedades. Por ejemplo, cuando propiedades como ``width`` o ``height`` cambian, empujan el contenido a su al rededor por el resto de la pagina. Esto fuerza a CSS a calcular nuevas posiciones para cada elemento afectado por el desplazamiento en cada frame de la transición. Debido a esto, cuando sea posible, es recomendable usar propiedades como ``transform`` y ``opacity`` en su lugar.

# 3. Estilos de texto

## 3.1 font-family
Se puede usar la regla `font-family` para cambiar el tipo de fuente del texto.

Por ejemplo, de esta forma podemos utilizar una `font-family` de tipo `sans-serif`.
```css
.ff-sans-serif {
  font-family: sans-serif;
}
```
A continuación un ejemplo de varios tipos de font-family distintos y sus posibles combinaciones.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="yLojraG" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/yLojraG">
  Text | font-family</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 3.2 font-style

También se puede cambiar el texto en italica, normal y cursiva, con la propiedad `font-style`

Para poner texto en itálica se utiliza

```css
.italic {
  font-style: italic;
}
```

Ejemplo de los tipos de font-style:

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="MWvGRjx" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/MWvGRjx">
  Text | font-style</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 3.3 font-weight

Para poner texto en negrita, o en una variante mas “ligera” se puede utilizar la propiedad `font-weight`.

Para poner el texto en negrita se utiliza 
```css
.fw-bold {
  font-weight: bold;
}
```

También se pueden poner en escalas del 100 al 900 de más finita a más gruesa.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="gOxKxNz" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/gOxKxNz">
  Text | font-weight numbers</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>


## 3.4 font-size

Para cambiar el tamaño del texto de se utiliza la propiedad `font-size`. Algunos de los valores absolutos son: `xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large`.

<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="eYEroda" data-editable="true" data-user="web-dot-dev" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/web-dot-dev/pen/eYEroda">
  Text | font-size keywords v2</a> by web.dev (<a href="https://codepen.io/web-dot-dev">@web-dot-dev</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

También es posible poner valores en `rem`, `em` y `px` para `font-size`.

> ¿Cuál es la diferencia entre `em` y `rem`? Respuesta: En CSS, `em` representa el `font-size` heredado del elemento padre. Por ejemplo, `font-size: 2em` equivale a el `font-size` del padre multiplicado por dos. rem es similar, pero representa el `font-size` del elemento raíz (root), es decir `<html>`.

Existen muchas posibilidades en cuanto a texto en CSS, para aprender mas sobre este tema recomendamos la lectura de https://web.dev/learn/css/typography.

# 4 Imágenes
vamos a ver cómo se tratan ciertos elementos especiales en CSS. Las imágenes y los vídeos se describen como elementos de reemplazo. Esto significa que el CSS no puede intervenir en aspectos del diseño interno de estos elementos, sino solo a su posición en la página y algunos otros aspectos. Sin embargo, como veremos, hay varias cosas que el CSS puede hacer con una imagen.

## 4.1 Tamaño de las imágenes
Todo en CSS genera una caja. Si colocas una imagen dentro de una caja que es más pequeña o más grande que las dimensiones intrínsecas del archivo de imagen en cualquier dirección, aparecerá más pequeño que la caja o se desbordará. Debes decidir qué hacer con el desbordamiento.

En el ejemplo siguiente hay dos cajas, ambas de 200 píxeles de tamaño.
Una es mas pequeña y no se expande, y la otra es mas grande y desborda

<iframe width="100%" height="1000" src="https://mdn.github.io/css-examples/learn/images/size.html" loading="lazy"></iframe>

### 4.1.1 Qué podemos hacer con el problema del desbordado?

una técnica común es hacer que el la propiedad max-width de una imagen sea 100%. Esto permite que la imagen tenga un tamaño menor que la caja.

Si añaden max-width: 100% al elemento img del ejemplo anterior. La imagen más grande se reduce hasta caber en la caja.

Puedes tomar otras decisiones sobre las imágenes dentro de los contenedores. Por ejemplo, es posible que desees cambiar el tamaño de una imagen para que cubra una caja por completo.

La propiedad object-fit puede ser de gran ayuda. Cuando se usa object-fit, el elemento de reemplazo puede dimensionarse para adaptarse a una caja de varias maneras.

<p class="codepen" data-height="300" data-default-tab="html" data-slug-hash="zYyBZzg" data-user="FRANCISCO-ANDRES-BERRUET-MARCHETTO" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/FRANCISCO-ANDRES-BERRUET-MARCHETTO/pen/zYyBZzg">
  Untitled</a> by FRANCISCO ANDRES BERRUET MARCHETTO (<a href="https://codepen.io/FRANCISCO-ANDRES-BERRUET-MARCHETTO">@FRANCISCO-ANDRES-BERRUET-MARCHETTO</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## 4.2 Cómo poner una imagen de fondo 
La propiedad CSS background-image establece una o más imágenes de fondo para un elemento.

Las imágenes de fondo se dibujan apilando capas de contexto una encima de la otra. La primera capa especificada se dibuja como si estuviera más cerca del usuario.

Cada imagen de fondo se especifica como la palabra clave none o como un valor image.

Para especificar varias imágenes de fondo, proporcione varios valores, separados por una coma

### 4.2.1 Ejemplo 

```html
<div>
  <p class="catsandstars">Este párrafo está lleno de gatos<br />y estrellas.</p>
  <p>Este párrafo no.</p>
  <p class="catsandstars">Aquí hay más gatos para ti.<br />¡Míralos!</p>
  <p>Y no mas.</p>
</div>
```
```css
p {
  font-size: 1.5em;
  color: #fe7f88;
  background-image: none;
  background-color: transparent;
}

div {
  background-image: url("mdn_logo_only_color.png");
}

.catsandstars {
  background-image: url("startransparent.gif"), url("catfront.png");
  background-color: transparent;
} 
```

[Resultado aca](https://developer.mozilla.org/es/docs/Web/CSS/background-image)
