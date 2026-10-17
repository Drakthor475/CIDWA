
El objetivo de estos dos temas es aprender a controlar cómo se comportan los elementos HTML y dónde se ubican dentro de una página web.

## `display`: cómo se distribuyen los elementos

La propiedad `display` define cómo se presenta un elemento y cómo participa en la distribución de los elementos que lo rodean.

Por ejemplo, imagina que tenemos tres elementos HTML: un título, un párrafo y un enlace. Aunque cada uno tiene un propósito diferente, CSS permite modificar cómo se distribuyen.

### `display: block`

Un elemento de tipo `block` comienza normalmente en una nueva línea y ocupa todo el ancho disponible de su contenedor, salvo que se limite su anchura.

![Pasted image 20261014172110](Img/Pasted%20image%2020261014172110.png)

- Para crear contenedores y secciones.
    
- Para organizar contenido verticalmente.
    
- Para que una tarjeta ocupe una fila completa.

### `display: inline`

Un elemento `inline` permanece dentro del flujo del texto. Ocupa el espacio necesario para su contenido y puede compartir la misma línea con otros elementos.

![Pasted image 20261014172323](Img/Pasted%20image%2020261014172323.png)

- Para resaltar palabras.
    
- Para incluir enlaces dentro de un párrafo.
    
- Para aplicar estilos a fragmentos de texto.
###  `display: inline-block`

Combina características de los dos anteriores: el elemento puede compartir una línea con otros, pero permite establecer dimensiones como un bloque.

![Pasted image 20261014172506](Img/Pasted%20image%2020261014172506.png)

- Para etiquetas pequeñas.
    
- Para botones o elementos que deben compartir una línea y tener dimensiones.
    
- Para componentes sencillos que no necesitan un sistema de distribución más avanzado.
### `display: none`

Hace que el elemento no se muestre y que no reserve espacio en la distribución de la página.

Ocultar un menú desplegable cuando está cerrado. 
## `position`: cómo ubicar los elementos

Ahora imagina que ya tienes una tarjeta de curso, pero quieres colocar una etiqueta «Nuevo» en su esquina. No quieres que la etiqueta empuje el título ni que altere la distribución de la tarjeta.
Para eso sirve `position`.
Las propiedades `top`, `right`, `bottom` y `left` permiten indicar desplazamientos o distancias, pero su efecto depende del valor de `position`.

### `position: static`

Es el comportamiento predeterminado de la mayoría de los elementos.

El elemento sigue el flujo normal del documento. Las propiedades `top`, `right`, `bottom` y `left` no lo desplazan cuando está en `static`.


### `position: relative`

El elemento conserva su espacio original en la página, pero puedes desplazarlo visualmente respecto a su posición inicial.

![Pasted image 20261014173040](Img/Pasted%20image%2020261014173040.png)

¿Como se desplaza?
```css
.tarjeta {
  position: relative;
  top: 10px;
  left: 15px;
}
```

   Sirve para :
- Para desplazar ligeramente un elemento.

- Para establecer una referencia de posicionamiento para elementos hijos con `position: absolute`.

- Para crear elementos decorativos dentro de una tarjeta.
### `position: absolute`

Permite ubicar un elemento fuera del flujo normal. Por eso, otros elementos se distribuyen como si ese elemento no estuviera ocupando su espacio.

Normalmente, el elemento se posiciona respecto al ancestro más cercano que establece su bloque contenedor de referencia. Un caso habitual es utilizar un padre con `position: relative`.

La etiqueta se coloca en una esquina de la tarjeta y no necesita empujar el título hacia abajo.

![Pasted image 20261014182308](Img/Pasted%20image%2020261014182308.png)


###  `position: fixed`

Posiciona el elemento respecto al área de visualización, normalmente la ventana del navegador. No reserva su espacio en el flujo normal y permanece en esa ubicación al desplazarse la página, salvo situaciones especiales relacionadas con sus ancestros.

![Pasted image 20261014182616](Img/Pasted%20image%2020261014182616.png)

## `position: sticky`

El elemento participa inicialmente en el flujo normal y puede quedarse fijado al alcanzar un límite de desplazamiento.
Con `top: 0`, el encabezado puede permanecer pegado a la parte superior al desplazarse la página, siempre que las condiciones de su contenedor y del desplazamiento lo permitan.

# Entendiendo `z-index`

La propiedad `z-index` sirve para controlar qué elemento aparece delante o detrás de otro cuando sus áreas se superponen.
#### ¿Cómo funcionan las capas?

Imagina que colocas varias hojas de papel una encima de otra. Aunque todas están en la misma superficie, algunas quedan delante y otras detrás.

En CSS ocurre algo parecido: los elementos pueden superponerse y el navegador determina cuál se muestra delante.



