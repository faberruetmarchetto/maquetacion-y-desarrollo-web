--- 
title: Clase 8 - Maquetacion y Desarrollo Web I 
description-meta: Clase 8
author-meta: Maquetacion y Desarrollo Web I
--- 

# 1. SEO (Search Engine Optimization)

El SEO (Optimización de motor de búsqueda) es el proceso de mejorar tu sitio para los motores de búsqueda (Google, DuckDuckGo, Bing, etc). 
Mejorar el SEO hace que tu sitio web aparezca en las búsquedas de dichos motores.

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

# 5. Herramientas para mejorar el SEO

Recomendamos la página [PageSpeed Insights](https://pagespeed.web.dev/) para analizar los sitios web y obtener recomendaciones y oportunidades de mejora.
Esta herramienta requiere que tu página ya se encuentre publicada para poder analizarla. Ya que es probable que no tengan ninguna página publicada, les recomendamos probar con wikipedia.org, para ver un ejemplo de análisis.

Esta herramienta analiza tu pagina web tanto para dispositivos móviles como para escritorio.
