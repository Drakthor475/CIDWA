El navegador representa cada elemento HTML como una caja rectangular para calcular su tamaño y su posición.
## Las cuatro partes de una caja

Cada elemento tiene cuatro capas conceptuales, desde el centro hacia afuera:

![[Pasted image 20261014143100.png]]

Parte       ¿Qué representa?

`content`  El contenido: texto, imagen u otros elementos.

`padding` El espacio entre el contenido y el borde de su propia caja. 

`border` El borde que rodea el contenido y su padding.

`margin` El espacio exterior que separa una caja de otras cajas o de su entorno.

No son intercambiables. Si quieres que el texto no quede pegado al borde de una tarjeta, utilizas `padding`. Si quieres separar esa tarjeta de otra, utilizas `margin` o alguna otra técnica de distribución, según el diseño.

### `padding`: el espacio que hay dentro de una caja


Se mide desde el borde de la propia caja hacia dentro.

![[Pasted image 20261014143650.png]]Puedes controlar cada lado por separado:
```css
.tarjeta {
  padding-top: 20px;
  padding-right: 16px;
  padding-bottom: 20px;
  padding-left: 16px;
}
```
O utilizar la forma abreviada:

|Código|Significado|
|---|---|
|`padding: 20px;`|Los cuatro lados.|
|`padding: 20px 12px;`|Arriba/abajo: 20px; izquierda/derecha: 12px.|
|`padding: 10px 16px 20px;`|Arriba: 10px; lados: 16px; abajo: 20px.|
|`padding: 10px 12px 14px 16px;`|Arriba, derecha, abajo e izquierda, en ese orden.|
## `margin`: la separación exterior entre cajas

Separa la caja de otras cajas o del espacio que la rodea.

![[Pasted image 20261014144142.png]]

¿De qué toma referencia `margin`?
El margen pertenece a la caja a la que se lo aplicas, pero su efecto se observa en relación con el espacio que la rodea y con las demás cajas. No es un espacio interior que se añade entre el texto y el borde.

>**IMPORTANTE**
> Los margenes pueden colapsar , `margin: 0 auto` puede centrar horizontalmente una caja de ancho limitado cuando existe espacio libre a ambos lados. No centra automáticamente su contenido ni la centra verticalmente.

Para evitar que el margen se colapse se utiliza `border-box`, ya que el ancho declarado incluye el contenido, el padding y el borde. 
