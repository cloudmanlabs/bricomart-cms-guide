---
layout: default
title: CMS BRICOMART
nav_order: 1
---

# GUIA PLANTILLA CMS BRICOMART
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

---


## HTML BÁSICO

### Texto normal

Todos los textos deberían siempre encerrados con alguna etiqueta. En general en texto normal debería encerrado en párrafos con el etiqueta `<p>`:

```html
<p>
  Texto de ejemplo.
</p>
```

### Negrita

```html
Este es <strong>un texto en negrita</strong>. También con <b>esta etiqueta</b>.
```

### Cursiva

```html
Este es <em>un texto en cursiva</em>. Tamnbién con <i>esta etiqueta</i>.
```

### Títulos

Para introducir títulos o titulares, tenemos las etiquetas  `<h1>`,  `<h2>` y  `<h3>`.  Están en orden de importancia, así que para el titular más importante utilizaremos `<h1>`, para titulares de una importancia secundaria `<h2>` y así sucesivamente:

```html
<h1>Titular de ejemplo.</h1>
```

### Enlaces

Para poner un enlace a otra página utilizaremos la etiqueta `<a>`. Esta etiqueta tiene un atributo imprescindible para que funcione, que es `href`. Dentro de ese atributo deberemos escribir la dirección completa a la página a la que queremos enlazar.

```html
<a href="https://www.bricomart.es/nuestros-almacenes/bm-valladolid.html" target="_blank">Almacén Valladolid</a>
```

### Imágenes

Cuando queramos agregar una imagen debemos utilizar la etiqueta `img`. No es necesario cerrar esta etiqueta, sin embargo sí es necesario poner el atributo `src` y muy recomendable poner el atributo `alt`.

En el atributo `src` deberemos colocar la URL completa de la imagen que queremos poner.

El atributo `alt` escribiremos un texto explicativo de la imagen, sirve para contextualizarla de cara a buscadores, lo que nos dará más presencia puntuación.

```html
<img src="https://www.bricomart.es/pub/media/wysiwyg/home/pedidos.png" alt="Bricomart Servicio de pedidos a distancia">
```

### Listas

```html
<ul>
  <li>Elemento 1</li>
  <li>Elemento 2</li>
  <li>Elemento 3</li>
</ul>
```

```html
<ol>
	<li>Elemento primero</li>
    <li>Elemento segundo</li>
</ol>
```





## MARCO GENERAL

Todo la página irá siempre dentro de un contendor, de eta manera:

```html
<div class="cms-container">
...
</div>
```

A partir de aquí, la página se compondrá de secciones. Hemos creado varios tipos de secciones para diferentes casos, las pasamos a describir.

## TIPOS DE SECCIONES

### TEXTO  ANCHO COMPLETO

Se puede utilizar esta sección para poner texto a una sola columna. El pantallas muy anchas el texto llegará al 70% del ancho para facilitar su legibilidad, y en pantallas más estrechas ocupará todo el ancho.

Para escribir secciones utilizaremos la etiqueta `<section>` con la clase `section-text-full`. Dentro de esta sección podremos poner el contenido que queramos. Lo normal será poner títulos `<h1>, <h2>, <h3>` y párrafos `<p>`. 

```html
<section class="section-text-full">
	<h1>Título</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipiscing elit id inceptos vitae.</p>
</section>
```

### BANNER

Se utiliza para poner un banner de ancho completo, es decir una imagen promocional que además se enlaza a otro sitio.

Esta es la estructura para la sección del banner será siempre la misma:

```html
<section class="section-banner">
    <a href="">
        <picture>
            <source media="(max-width:576px)" srcset="img/banner-mobile.png">
            <source media="(max-width:768px)" srcset="img/banner-tablet.png">
            <img src="img/banner-desktop.png" alt="">
        </picture>
    </a>
</section>
```

Debemos escribir la dirección del enlace a al que queremos dirigir el banner en el atributo `href` de la etiqueta `<a>`.

Tenemos la posibilidad de introducir 3 formatos de imagen diferente para que se muestre la adecuada en función del ancho de la pantalla. Escribiremos la dirección del enlace a la imagen que queremos que se muestre en el contexto de pantalla más ancha, en el atributo `src`de la etiqueta `<img>`. De la misma manera pondremos el enlace a la imagen de tamaño medio y pequeño en los atributos `srcset` de las etiquetas `<source>`. 

### MENU

Con este tipo de sección podemos crear un menú que enlace a otras secciones de nuestra página:

```html
<section class="section-menu">
    <a href="#section-enlazada">¿Cómo llegar?</a>
    <a href="#">Nuestras soluciones</a>
    <a href="#">Servicio de pedidos</a>
    <a href="#">Nuestros compromisos</a>
    <a href="#">Fomentamos empleo</a>
</section>
```

Solamente necesitamos crear una `section` con la clase `section-menu` y dentro poner los enlaces (anchor) que deseemos a las diferentes secciones.

En el atributo `href` de los enlaces tendremos que poner `#` y el identificador de la sección a la que queremos enlazar:

```html
<section id="section-enlazada" class="section-text-full">
    ...
</section>
```

### ELEMENTO FLOTANTE

Esta sección es para poner texto al rededor de un elemento, que puede ser una imagen u otra cosa, como un mapa de Google Maps o un vídeo de Youtube.

Para ello, lo primero es crear una sección con la clase `section-float`:

```html
<section class="section-float">
    <img class="item-float item-left" src="https://imagen.jpg" alt="Texto alt">
    <h1>Sección imagen texto izquierda</h1>
    <p>
        Lorem ipsum dolor sit amet consectetur adipiscing elit id inceptos vitae 			potenti lacinia hendrerit, ut mi duis gravida parturient eget montes erat 			varius platea et mus. Vitae sociosqu sapien massa ut augue pretium quis 			aptent ornare, consequat purus porttitor dictum facilisis curabitur potenti 		justo mauris proin, tincidunt egestas iaculis aliquet eget nulla mus mi. 			Mattis cum nam taciti facilisi praesent congue    porttitor tempus molestie 		vehicula dapibus maecenas penatibus per, lobortis felis condimentum habitasse 			aliquet curae morbi ridiculus euismod ultricies orci dignissim.
    </p>
    <div class="clear"></div>
  </section>
```

La clave de esta sección es que el elemento al rededor del que el texto va a flotar, debe llevar la clase `item-float` además de la clase `item-left` si queremos que el elemento quede a la izquierda o `item-right` si queremos que quede a la derecha. 

Existe otra particularidad de esta sección, y es que es imperdible que el último elemento de la sección sea este:

```html
<div class="clear"></div>
```

### COLUMNAS

Esta sección es para poner un contenido en varias columnas de igual tamaño, por ejemplo dos imágenes.

```html
<section class="section-columns">
    <img class="img-fluid" src="https://imagen1.jpg" alt="">
    <img class="img-fluid" src="https://imagen2.jpg" alt="">
    <div>
        <h2>
            Titular
        </h2>
        <p>
             Lorem ipsum dolor sit amet consectetur adipiscing elit id inceptos vitae <a href="">Hola</a>
        </p>
    </div>
</section>
```

Debemos crear una sección con la clase `section-columns` y, simplemente todos  elementos dentro de esta sección se colocarán en columnas.

## UTILIDADES

### IMAGEN FLUIDA

Cuando queramos que una imagen ocupe todo el ancho, por ejemplo de una columna, deberemos establecerle la clase `img-fluid`. Es recomendable para las imágenes que vayan en secciones de columnas.

```html
<img class="img-fluid" src="https://imagen1.jpg" alt="">
```

### EMBEBIDOS ADAPTATIVOS

Cuando metamos un embebido, por ejemplo un video de YouTube o un Mapa, deberemos seguir esta estructura para que sea adaptativo, y no tenga un tamaño fijo:

```html
<div class="embed-responsive embed-responsive-16by9">
      <iframe class="embed-responsive-item" 	            src="https://www.youtube.com/embed/ku7nSTJDDUE"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen></iframe>
 </div>
```

Deberemos seguir esta estructura y poner todas las clases que figuran. Otra cosa importante es quitar los atributos `width` y `height` que suelen venir en el código que proporciona Google a la hora de compartir este tipo de elementos.

### ACORDEÓN

Tenemos una utilidad de "acordeón" o "información desplegable". Esta es su estructura:

```html
   <div class="tabs">
      <div class="tab">
        <input class="cms-accordition-input" type="checkbox" id="chck1">
        <label class="tab-label" for="chck1">Item 1</label>
        <div class="tab-content">
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Ipsum, reiciendis!
        </div>
      </div>
      <div class="tab">
        <input class="cms-accordition-input" type="checkbox" id="chck2">
        <label class="tab-label" for="chck2">Item 2</label>
        <div class="tab-content">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. A, in!
        </div>
      </div>
    </div>
```

Esta estructura es necesaria y hemos de incluirla cada vez que se desee un comportamiento de este tipo. 

Para cada desplegable que deseemos debemos crear una `div` con la clase `tab` y toda la estructura dentro.

### ALINEAR TEXTO

Texto alineado a la derecha:

```html
<h2 class="text-right">Titulo</h2>
```

Texto alineado a la izquierda:

```html
<h2 class="text-left">Titulo</h2>
```

Texto centrado:

```html
<h2 class="text-center">Titulo</h2>
```

### VARIANTES  DE COLOR

Texto en color primario (azul):

````html
<h2 class="text-primary">Titulo</h2>
````

Texto en color secundario (naranja):

````html
<h2 class="text-secondary">Titulo</h2>
````
