
##  ¿Qué es HTML?

**HTML**  significa *HyperText Markup Language* (lenguaje de marcado dehipertexto).
Se utiliza para definir la **estructura y el contenido** de una página web.

Con HTML indicamos qué elementos contiene una página: títulos, párrafos, enlaces, 
imágenes y contenedores.

HTML no es un lenguaje de programación, sino un ***lenguaje de marcado**.
Define la estructura; CSS controla la presentación visual y JavaScript permite 
agregar comportamientos e interacciones.

  

## ¿Qué es una etiqueta?

Muchas etiquetas tienen apertura y cierre:

``` html

<p>Este es un párrafo.</p>

```

-   `<p>`: etiqueta de apertura.

-   `Este es un párrafo.`: contenido.

-   `</p>`: etiqueta de cierre.

El conjunto forma un **elemento HTML**. Algunos elementos, como `img`, no llevan etiqueta de cierre:

``` html

<img src="guitarra.jpg" alt="Guitarra eléctrica">

```

### Atributos
Los atributos proporcionan información adicional dentro de la etiqueta
de apertura.

``` html

<a href="https://example.com">Visitar sitio</a>

```


-   `href` indica el destino del enlace.

-   `src` indica la ruta o URL de una imagen.

-   `alt` describe una imagen mediante texto.
##  Estructura básica de un documento HTML

``` html

<!DOCTYPE html>

<html lang="es">

<head>

  <meta charset="UTF-8">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Mi primera página</title>

</head>

<body>

  <h1>Mi primera página web</h1>

  <p>Estoy aprendiendo HTML en CIDWA.</p>

</body>

</html>

```

  -----------------------------------------------------------------------

	  Elemento                            Función

  ----------------------------------- -----------------------------------

  `<!DOCTYPE html>`                   Indica que el documento utiliza   HTML moderno.


  `<html lang="es">`                 Elemento raíz `lang` declara el idioma principal.


  `<head>`                                     Contiene metadatos y recursos de configuración.

  

  `<meta charset="UTF-8">`      Permite representar correctamente caracteres como acentos y ñ.


  `<meta name="viewport"...>` Ayuda a adaptar la página al ancho de dispositivos móviles.

  `<title>`                                     Define el título que suele aparecer en la pestaña del navegador.


  `<body>`                                     Contiene el contenido de la página.


  `<h1>`                                         Encabezado principal.

  `<p>`                                          Párrafo.

  -----------------------------------------------------------------------

### Diferencia entre `head` y `body`

-   **`head`**:**** información sobre el documento y recursos que utiliza.

-   **`body`**:**** contenido de la página, como títulos, texto, imágenes y enlaces****.


El texto de `title` normalmente aparece en la pestaña del navegador, no como un título dentro del contenido de la página.
## Etiquetas iniciales

### Encabezados: `h1` a `h6`

Organizan títulos y subtítulos por nivel.

``` html

<h1>Mi sitio personal</h1>

<h2>Mis gustos</h2>

<h3>Música favorita</h3>

```


Elige el nivel según la jerarquía del contenido, no solamente por el tamaño predeterminado. CSS puede modificar su apariencia.
### Párrafos: `p`

``` html

<p>Me gusta escuchar rock mientras estudio.</p>

```
### Enlaces: `a`

``` html

<a href="https://es.wikipedia.org/wiki/Rock">

  Conocer más sobre el rock

</a>

```


Un enlace permite navegar a un destino. Aunque CSS pueda hacer que se

vea como un botón, sigue siendo un enlace.

### Imágenes: `img`

``` html

<img src="guitarra.jpg" alt="Guitarra eléctrica">

```


Comprueba que la ruta exista. El `alt` debe describir el contenido o función de la imagen.


### Listas : `ul, ol and  li`

Representan listas tanto ordenadas  `ol`  como desordenadas  `ul` , se representan como viñetas en caso de ser desornedas  y como numeros (1,2,3 ) , posterior a eso los elementos de las listas se presesentan como `li` .

```html
<h3 class='titulo-receta'> Receta pay de limon </h3>

<ul class='ingredientes'>
<li>Galletas Maria</li>
<li>Limon</li>
<li>Queso</li>
<li>Leche</li>
<li>Lechera</li>
</ul>

<h3 class='titulo-receta'> Pasos para preparar </h3>

<ol class='pasos'>
<li>Batir el limon, levhe,queso y lechera</li>
<li>Poner una capa de galletas en un refractario</li>
<li>Cubrir la primera capa de galletas con la mezcla</li>
...

</ol>


```



##  Conectar HTML con CSS

Para utilizar una hoja de estilos externa, coloca un enlace dentro de `head`:


``` html

<head>

  <meta charset="UTF-8">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Mi tarjeta</title>

  <link rel="stylesheet" href="styles.css">

</head>

```
  
Si `styles.css` está en la misma carpeta que el archivo HTML,

`href="styles.css"` funciona.

Ejemplo de CSS:

``` css

.tarjeta {

  background-color: white;

  padding: 20px;

  border-radius: 12px;

}

.tarjeta h2 {

  color: #1e293b;

}

.tarjeta p {

  line-height: 1.6;

}

```

  
## ¿Qué es un contenedor `div`?

Un `div` es un contenedor genérico que permite agrupar elementos HTML. Por sí mismo no representa un contenido específico ni tiene un diseño visual especial.

```html
<div class="tarjeta">
  <h2>Rock</h2>
  <p>Me gusta por su energía y sus letras.</p>
</div>
```

En este ejemplo:
- `div` agrupa el contenido.
- `class="tarjeta"` identifica el contenedor para aplicar estilos.
- `h2` representa el título.
- `p` contiene la descripción.

La clase no modifica la apariencia por sí sola. Es CSS quien define cómo se verá el contenedor.

### Qué significa anidar contenedores?

Anidar significa colocar un elemento dentro de otro. Esto permite dividir una interfaz en secciones más pequeñas.

![Pasted image 20261014141618](Img/Pasted%20image%2020261014141618.png)

Codigo equivalente:
```html
<div class="tarjeta">
  <img src="guitarra.jpg" alt="Guitarra eléctrica">

  <div class="contenido">
    <h2>Rock</h2>
    <p>Me gusta por su energía.</p>
    <a href="https://es.wikipedia.org/wiki/Rock">
      Conocer más
    </a>
  </div>
</div>
```
¿Por qué utilizar dos `div`?

- `.tarjeta` controla la apariencia general.
    
- `.contenido` permite aplicar estilos solo al título, la descripción y el enlace agrupados.

No es obligatorio crear un contenedor por cada elemento. Se crean cuando ayudan a organizar el contenido o a controlar su presentación.

