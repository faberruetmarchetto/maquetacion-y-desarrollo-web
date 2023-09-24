---
title: Clase 8 - Maquetacion y Desarrollo Web I
description-meta: Clase 8
author-meta: Maquetacion y Desarrollo Web I
---

# 1. SEO (Search Engine Optimization)

La optimización de motores de búsqueda (SEO) es la práctica de optimizar el contenido, la estructura y la presencia general en línea de un sitio web para mejorar su visibilidad y clasificación en las páginas de resultados de los motores de búsqueda (como Google, DuckDuckGo, Bing, etc).

Implica técnicas como investigación de palabras clave, optimización en la página, construcción de enlaces para hacer que el sitio web sea atractivo tanto para los motores de búsqueda como para los usuarios.

Las empresas recurren a mejorar el SEO para ser encontradas y captar la demanda. Lo que puede aumentar el tráfico del sitio web, generar conversiones y aumentar las ventas.


# 2. Glosario

Términos importantes:

* **Index** Google guarda las páginas web en su index (índice). La entrada para cada página describe el contenido y la URL de la página. Google indexa cuando procesa una página y la agrega a su índice.
* **Crawl** El proceso de buscar nuevas páginas (o actualizaciones). Google descubre las URLs siguiendo links, y leyendo otros datos.
* **Crawler** Software automatizado que busca las páginas y las indexa.
* **Googlebot** Nombre genérico del crawler de Google.

# 3. Mi sitio está indexado?

**¿Cómo determinar si mi sitio está indexado en Google?**.

Buscando `site:` + la URL de mi sitio. Si encontras resultados, significa que el sitio está indexado. Por ejemplo: `site:wikipedia.org`.

# 4. ¿Cómo hago que mi sitio aparezca en Google?

Google es un motor de búsqueda automatizado que usa web crawlers para explorar la web de forma constante, buscando sitios para agregar a su indice.
Usualmente no es necesario hacer nada mas que publicar el sitio para que aparezca en Google.
Una forma de hacer que Google encuentre tu contenido es con ‘sitemaps’. [Recomendamos leer mas sobre sitemaps aca](https://developers.google.com/search/docs/crawling-indexing/sitemaps/overview?hl=es).

## 4.1 Algunos consejos

### Crea títulos de página únicos y precisos

Un elemento `<title>` indica a los usuarios y a los buscadores el tema de una página concreta. Coloca el elemento `<title>` dentro del elemento `<head>` del documento HTML y crea un texto de título único para cada página de tu sitio.

```html
<html>
<head>
    <title>Brandon's Baseball Cards - Buy Cards, Baseball News, Card Prices</title>
    <meta name="description" content="Brandon's Baseball Cards provides a large selection of
    vintage and modern baseball cards for sale.
    We also offer daily baseball news and events.">
</head>
<body>
…
```
### Influir en los enlaces de título y los fragmentos en los resultados de búsqueda

Si tu documento aparece en una página de resultados de búsqueda, es posible que el contenido del elemento `<title>` aparezca como enlace de título del resultado de búsqueda.
Si no conoces las diferentes partes de un resultado de búsqueda de Google, consulta el vídeo sobre sus componentes.

[](https://developers.google.com/static/search/docs/images/title.png?hl=es)

El elemento `<title>` de una página principal puede incluir el nombre del sitio web o de la empresa, así como otros datos importantes, como la ubicación física de la empresa o algunas de sus principales especialidades u ofertas.

### Describe con precisión el contenido de la página

Elige un título que resulte natural y comunique de forma eficaz el tema del contenido de la página.

Qué debes evitar:

* Utilizar texto en el elemento `<title>` que no tenga relación con el contenido de la página.
* Utilizar textos predeterminados o imprecisos, como "Sin título" o "Página nueva 1".

### Crea elementos `<title>` únicos para cada página

Comprueba que cada página de tu sitio tenga texto único en el elemento `<title>`, ya que así ayudas a Google a saber en qué se diferencia una página de las otras. Si tu sitio tiene páginas para móviles independientes, recuerda utilizar texto descriptivo también en los elementos `<title>` de las versiones para móviles.

Qué debes evitar:

* Utilizar un mismo título en todos los elementos de las páginas de tu sitio o de un gran número de ellas.

### Utiliza elementos `<title>` breves pero descriptivos

Los elementos `<title>` pueden ser breves e informativos a la vez. Si el texto del elemento `<title>` es demasiado largo o se considera que incluye información poco pertinente, es posible que Google muestre solo una parte del texto en el elemento `<title>` o un enlace de título que se genere automáticamente en el resultado de búsqueda.

Qué debes evitar:

* Utilizar texto demasiado largo en los elementos `<title>` que no resulte útil a los usuarios.
* Añadir palabras clave innecesarias al elemento `<title>`.

### Utiliza la etiqueta de metadescripción

La etiqueta de metadescripción de una página ofrece a Google y a otros buscadores un resumen del contenido de la página. El título de una página puede estar formado por unas cuantas palabras o por una frase, mientras que la etiqueta de metadescripción de una página puede contener una frase o dos, o incluso un párrafo breve.
Al igual que el elemento `<title>`, la etiqueta de metadescripción se coloca dentro del elemento `<head>` del documento HTML.

```html
<html>
<head>
    <title>Brandon's Baseball Cards - Buy Cards, Baseball News, Card Prices</title>
    <meta name="description" content="Brandon's Baseball Cards provides a large selection of vintage and modern baseball cards for sale. We also offer daily baseball news and events.">
</head>
<body>
...
```

#### ¿Cuáles son las ventajas de las etiquetas de metadescripción?

Las etiquetas de metadescripción son importantes porque Google puede utilizarlas como fragmentos de tus páginas en los resultados de búsqueda de Google. Ten en cuenta que Google puede considerar que es mejor utilizar una sección relevante del texto visible de una página si este es muy similar a la consulta de un usuario. Te recomendamos añadir etiquetas de metadescripción en todas las páginas por si Google no encuentra un texto adecuado que incluir en el fragmento. Más información sobre cómo crear metadescripciones de calidad

> Hay muchisimas mas recomendaciones aplicables.
En particular, recomendamos leer las [propuestas de Google](https://developers.google.com/search/docs/fundamentals/seo-starter-guide?hl=es#understand_your_content).

#### Resumir de forma precisa el contenido de la página

Describe e informa a los usuarios del contenido de tu sitio de un modo que capte su interés si la etiqueta de metadescripción aparece como fragmento en un resultado de búsqueda. Si bien no hay requisitos de longitud concretos en el texto de una etiqueta ```meta``` ```description```, te recomendamos que compruebes que tenga la longitud adecuada para mostrarse por completo en la Búsqueda (tene en cuenta que el tamaño de los fragmentos varía en función de cómo y dónde se realice la búsqueda). También debes asegurarte de que contenga toda la información necesaria para que los usuarios determinen si la página es útil y relevante.

Qué debes evitar:

* Escribir una etiqueta de metadescripción que no tenga relación con el contenido de la página.
* Proporcionar descripciones generales, como "Esto es una página web" o "Página sobre figuritas de futbol".
* Rellenar la descripción solo con palabras clave.
* Copiar y pegar todo el contenido del documento en la etiqueta de metadescripción.

#### Usar descripciones únicas en cada página

Al tener una etiqueta de metadescripción diferente en cada página, ayuda tanto a los usuarios como a Google, sobre todo si los usuarios hacen búsquedas que devuelven varias páginas de tu dominio (por ejemplo, búsquedas con el operador ```site:```). Si tu sitio tiene miles o incluso millones de páginas, es poco probable que puedas escribir a mano las etiquetas de metadescripción de todas ellas. En este caso, se puede optar por generar automáticamente etiquetas de metadescripción que se basen en el contenido de cada página.

Qué debes evitar:

* Utilizar una única etiqueta de metadescripción en todas las páginas de un sitio o en un gran número de ellas.

### Añadir etiquetas de encabezado para destacar el texto importante

Con los encabezados adecuados, puedes indicar los temas importantes y crear una estructura jerárquica de tu contenido, de modo que los usuarios puedan navegar por el documento con más facilidad.

#### Hacer un esquema

Considera cuáles son los puntos principales y secundarios del contenido de la página y, en función de ello, decide dónde utilizar etiquetas de encabezado.

Qué debes evitar:

* Escribir texto que no ayude a definir la estructura de la página.
* Incluir etiquetas de encabezado en lugares en los que otras etiquetas, como ```<em>``` y ```<strong>```, serían más adecuadas.
* Variar los tamaños de las etiquetas de encabezado de forma poco coherente.

#### No poner demasiados encabezados en una pagina

Utiliza etiquetas de encabezado cuando creas que es pertinente, pero tene en cuenta que si incluis demasiadas en una página, a los usuarios les costará distinguir de un vistazo dónde comienza o termina cada tema.

Qué debes evitar:

* Incluir demasiadas etiquetas de encabezado en una página.
* Escribir encabezados muy largos.
* Usar etiquetas de encabezado solo para añadir estilo al texto, sin definir una estructura.

# 5. Herramientas para mejorar el SEO

Recomendamos la página [PageSpeed Insights](https://pagespeed.web.dev/) para analizar los sitios web y obtener recomendaciones y oportunidades de mejora.
Esta herramienta requiere que tu página ya se encuentre publicada para poder analizarla. Ya que es probable que no tengan ninguna página publicada, les recomendamos probar con wikipedia.org, para ver un ejemplo de análisis.

Esta herramienta analiza tu página web tanto para dispositivos móviles como para escritorio.

# 6. Añadir marcado de datos estructurados

Los datos estructurados son fragmentos de código que podes añadir a las páginas de tu sitio para describir su contenido y ayudar a que los buscadores comprendan mejor lo que contienen. Con esta información, los buscadores pueden mostrar el contenido de forma más útil (y llamativa) en los resultados de búsqueda, lo que puede ayudarte a atraer a los clientes adecuados para tu empresa.
Por ejemplo, supongamos que tenemos una tienda online y que etiquetamos una página de producto concreto; al hacerlo, ayuda a saber que en esa página aparece una bicicleta, su precio y reseñas de clientes. Es posible que mostremos esta información en el fragmento de los resultados de búsqueda de las consultas relevantes. Estos resultados se denominan "resultados enriquecidos".
Además de utilizar el marcado de datos estructurados para mostrar resultados enriquecidos, es posible que los usemos para servir resultados relevantes en otros formatos. Por ejemplo, el propietario de una tienda mas tradicional puede etiquetar las horas de apertura; de este modo los clientes potenciales pueden encontrarte cuando lo necesiten y saber si está abierto o cerrado en el momento exacto de la búsqueda.

Algunas etiquetas relevantes podrian ser:

* Productos que vendes
* Ubicación de la empresa
* Vídeos sobre tus productos o tu empresa
* Horarios de apertura
* Listas de eventos

[Lista completa de los tipos de contenido disponibles](https://developers.google.com/search/docs/appearance/structured-data/search-gallery?hl=es "Lista completa de los tipos de contenido disponibles")

#### Gestionar cómo aparece un sitio web en los resultados de búsqueda

Al añadir correctamente datos estructurados a tus páginas, estas también pueden beneficiarse de muchas funciones especiales en los resultados de búsqueda de Google, como la valoración en estrellas, resultados con estilo y mucho más.

# 7. Organizar la jerarquia de mi sitio

#### ¿Como utilizan los buscadores las URL?

Los buscadores necesitan una URL única por fragmento de contenido para poder rastrear e indexar dicho contenido y remitir a los usuarios a él. Los diferentes contenidos (por ejemplo, los distintos productos de una tienda), así como el contenido modificado (por ejemplo, las traducciones o variaciones regionales de una página) deben utilizar URLs diferentes para que aparezcan correctamente en la búsqueda.

Las URLs se dividen generalmente en varias secciones distintas:
```https://www.example.com/RunningShoes/Womens.htm?size=8#info```

* Google recomienda que todos los sitios web utilicen ```https://``` siempre que sea posible.
* El nombre de host es donde se aloja un sitio web y normalmente es el mismo nombre de dominio que se utiliza en el correo.
* Google distingue entre las versiones con ```www``` y sin ```www``` (por ejemplo, ```www.example.com``` o solo ```example.com```).
* La ruta, el nombre del archivo y la cadena de consulta determinan a qué contenido de un servidor se accede. Estos tres elementos distinguen entre mayúsculas y minúsculas, por lo que ```FILE``` dará como resultado una URL distinta que ```file```.
* En el nombre de host y en el protocolo no se distingue entre mayúsculas y minúsculas.
* Por lo general, los fragmentos (señalados en la url con un ```#```) identifican a qué parte de la página se desplaza el navegador. Dado que normalmente el contenido es el mismo independientemente del fragmento, los buscadores suelen ignorarlos.
* Cuando se hace referencia a la página principal, una barra inclinada posterior al nombre de host es opcional, ya que lleva al mismo contenido ```(https://example.com/``` es lo mismo que ```https://example.com)```. 

En el caso de la ruta y el nombre de archivo, una barra inclinada posterior se vería como una URL diferente (que indica un archivo o un directorio); por ejemplo, ```https://example.com/fish``` no es lo mismo que ```https://example.com/fish/```.

#### La navegación es importante para los buscadores

La navegación de un sitio web es importante porque ayuda a los visitantes a encontrar el contenido que buscan. Además, contribuye a que los buscadores sepan qué contenido considera importante el propietario del sitio web. Aunque los resultados de búsqueda de Google muestran información a nivel de página, a Google también le gusta saber en términos generales qué función tiene una página en el conjunto del sitio.

##### Ejemplo de estructura interna

[![Ejemplo de estructura interna](https://lh3.googleusercontent.com/FkXf1NMLRBDRD0-82WWHYCu7_nHxCzkUaMDFDAuGiFRYIrtgO3wqSJdtSFhpnyu3yeE=w314 "Ejemplo de estructura interna")](https://lh3.googleusercontent.com/FkXf1NMLRBDRD0-82WWHYCu7_nHxCzkUaMDFDAuGiFRYIrtgO3wqSJdtSFhpnyu3yeE=w314 "Ejemplo de estructura interna")

#### Planificar la navegación a partir de la página principal

Todos los sitios tienen una página principal o de inicio, que suele ser la página más visitada y el punto de partida de la navegación. A no ser que tu sitio tenga pocas páginas, es importante pensar en cómo van a ir los visitantes de la página principal (de inicio) a una página con contenido más específico.
¿Tenes suficientes páginas sobre un área temática específica para crear otra página en que se describan las páginas relacionadas (por ejemplo, página de inicio > lista de temas relacionados > tema específico)?
¿Tienes cientos de productos diferentes que deben clasificarse en diferentes categorías y subcategorías?

#### Usa listas de rutas de exploración

Una ruta de exploración es una fila de enlaces internos situada en la parte superior o inferior de una página que permite a los visitantes volver rápidamente a una sección anterior o a la página de inicio. En muchas rutas de exploración, la página más general (normalmente, la página de inicio) es el primer enlace y se sitúa a la izquierda; las secciones más concretas se van enumerando hacia la derecha.

##### Ejemplo

[![Ejemplo](https://lh3.googleusercontent.com/iRXf8tJ7BTCs_Uwd4U2TgIKTXp_KOP8B-HGo-oqQ4ktQWdVQXKeZZbglL0QxOk6sdg=w650 "Ejemplo")](https://lh3.googleusercontent.com/iRXf8tJ7BTCs_Uwd4U2TgIKTXp_KOP8B-HGo-oqQ4ktQWdVQXKeZZbglL0QxOk6sdg=w650 "Ejemplo")

Al mostrar las rutas de exploración, te recomendamos que utilices el [marcado de datos estructurados correspondiente](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb?hl=es "marcado de datos estructurados correspondiente").

#### Crea una página de navegación sencilla para los usuarios

Una página de navegación es una página sencilla de un sitio web que muestra la estructura del sitio web y que normalmente consiste en una lista jerárquica de las páginas que se incluyen en este. Es posible que los visitantes consulten esta página si no pueden encontrar algunas páginas del sitio web.
Aunque los buscadores también la visitan, lo que les permite rastrear eficazmente las páginas de un sitio, esta página suele estar dirigida a los visitantes.

#### La  arquitectura debe ser fluida y natural

Facilita al máximo que los usuarios puedan ir del contenido general al contenido más específico que les interese de tu sitio. Añade páginas de navegación cuando sean necesarias e intégralas de forma eficaz en la estructura de enlaces internos. Comprueba que se puede acceder a todas las páginas de tu sitio mediante enlaces y que no es necesario recurrir a funciones de búsqueda interna para encontrarlas. Incluye enlaces a páginas relacionadas, si resulta pertinente, para que los usuarios puedan descubrir contenido similar.

Qué debes evitar:

* Crear redes de enlaces de navegación complejas, por ejemplo, enlazando todas las páginas entre sí.
* Dividir y separar en exceso el contenido (por ejemplo, 20 clics son demasiados para ir de la página principal a una en concreto).

#### Utilizar texto en la navegación

Si controlas casi toda la navegación de un sitio con enlaces de texto, los buscadores pueden rastrearlo e interpretarlo con más facilidad. Si creas una página con JavaScript, utiliza elementos ```a``` con URLs en los valores del atributo ```href``` y genera todos los elementos de menú al cargar la página, no cuando el usuario interactúe con la página.

Qué debes evitar:

* Utilizar una navegación que se base completamente en imágenes o animaciones.
* [Requerir gestiones de eventos basadas en secuencias de comandos de la navegación](https://developers.google.com/search/docs/crawling-indexing/links-crawlable?hl=es#crawlable-links "Requerir gestiones de eventos basadas en secuencias de comandos de la navegación").

#### Las URLs sencillas transmiten información sobre el contenido

Al crear categorías descriptivas y nombres de archivo en los documentos de tu sitio web, no solo organizas mejor el sitio web, sino que te permite generar URLs más sencillas a los quieran enlazar a tu contenido. Es posible que las URLs extremadamente largas y crípticas que contengan pocas palabras reconocibles intimiden a los visitantes.

Las URLs como la que se muestran a continuación pueden ser confusas y difíciles de utilizar: ```https://www.ejemplo.com/folder1/22447478/x2/14032015.html```. 
Si tu URL es descriptiva, puede ser más útil y fácil de entender en contextos diferentes: ```https://www.ejemplo.com/article/mejores-jugadores-del-futbol.html```

#### Las URLs se muestran en los resultados de búsqueda

Por último, recuerda que la URL de un documento suele mostrarse en los resultados de la Búsqueda de Google cerca del título del documento. Google puede rastrear todo tipo de estructuras de URL, incluso las más complejas; sin embargo, recomendamos que dediques tiempo a simplificarlas al máximo.
Las URLs que contienen palabras relevantes para el contenido y la estructura del sitio web resultan más atractivas a los visitantes que navegan por este.

Qué debes evitar:

* Utilizar URLs muy largas con parámetros innecesarios e IDs de sesión.
* Elegir nombres genéricos de páginas
* Usar demasiadas palabras clave
