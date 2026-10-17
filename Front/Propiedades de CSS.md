
## Texto

|Propiedad|Función|Ejemplo|
|---|---|---|
|`font-family`|Tipo de letra|`font-family: Arial, sans-serif;`|
|`font-size`|Tamaño del texto|`font-size: 18px;`|
|`font-weight`|Grosor de letra|`font-weight: bold;`|
|`color`|Color del texto|`color: #2563eb;`|
|`text-align`|Alineación del texto|`text-align: center;`|
|`text-decoration`|Decoración o subrayado|`text-decoration: none;`|
|`text-transform`|Mayúsculas/minúsculas|`text-transform: uppercase;`|
|`line-height`|Altura entre líneas|`line-height: 1.6;`|
|`letter-spacing`|Espacio entre letras|`letter-spacing: 1px;`|
|`text-shadow`|Sombra del texto|`text-shadow: 1px 1px 2px #aaa;`|

## Imágenes

|Propiedad|Función|Ejemplo|
|---|---|---|
|`width`|Ancho|`width: 100%;`|
|`height`|Altura|`height: 180px;`|
|`max-width`|Ancho máximo|`max-width: 100%;`|
|`object-fit`|Ajuste de la imagen|`object-fit: cover;`|
|`object-position`|Posición del recorte|`object-position: center;`|
|`border-radius`|Esquinas redondeadas|`border-radius: 8px;`|
|`display`|Tipo de presentación|`display: block;`|

##  Enlaces (`a`)

|Propiedad|Función|Ejemplo|
|---|---|---|
|`color`|Color del enlace|`color: #2563eb;`|
|`text-decoration`|Controla el subrayado|`text-decoration: none;`|
|`font-weight`|Grosor del texto|`font-weight: bold;`|
|`font-size`|Tamaño del texto|`font-size: 16px;`|
|`background-color`|Color de fondo|`background-color: #2563eb;`|
|`padding`|Espacio interior|`padding: 10px 14px;`|
|`border-radius`|Redondea las esquinas|`border-radius: 7px;`|
|`display`|Controla su presentación|`display: inline-block;`|
|`:hover`|Estilo al pasar el cursor|`a:hover { color: red; }`|

## Listas (`ul`, `ol`, `li`)

|Propiedad|Función|Ejemplo|
|---|---|---|
|`list-style-type`|Tipo de viñeta o numeración|`list-style-type: square;`|
|`list-style-position`|Posición de la viñeta|`list-style-position: inside;`|
|`list-style-image`|Imagen como viñeta|`list-style-image: url("icono.png");`|
|`padding-left`|Espacio izquierdo|`padding-left: 20px;`|
|`margin`|Espacio exterior|`margin: 10px;`|
|`color`|Color del texto|`color: #334155;`|
|`line-height`|Separación entre líneas|`line-height: 1.6;`|
## Propiedades CSS que pueden aplicarse directamente a un `div`

|Propiedad|Función|Ejemplo|
|---|---|---|
|`background-color`|Cambia el color de fondo.|`background-color: white;`|
|`color`|Define el color del texto heredable.|`color: #334155;`|
|`width`|Define el ancho.|`width: 300px;`|
|`height`|Define la altura.|`height: 200px;`|
|`min-height`|Establece una altura mínima.|`min-height: 150px;`|
|`padding`|Añade espacio interior.|`padding: 20px;`|
|`margin`|Añade espacio exterior.|`margin: 16px;`|
|`border`|Define el borde.|`border: 1px solid #ddd;`|
|`border-radius`|Redondea las esquinas.|`border-radius: 12px;`|
|`box-shadow`|Añade una sombra.|`box-shadow: 0 4px 12px #0002;`|
|`text-align`|Alinea el texto dentro del contenedor.|`text-align: center;`|
|`font-family`|Define la tipografía heredable.|`font-family: Arial, sans-serif;`|
|`overflow`|Controla el contenido que sobresale.|`overflow: hidden;`|

Importante: no todas las propiedades afectan exclusivamente al `div`. Por ejemplo, `color` y `font-family` suelen heredarse por los elementos de texto que están dentro del contenedor.

## Posicionamiento

`position: relative`
Conserva el espacio original y permite desplazar el elemento. También puede establecer una referencia para descendientes absolutos.
`position: absolute`
Permite ubicar un elemento fuera del flujo normal.

`position: fixed`
Mantiene el elemento anclado a la ventana en condiciones habituales.

`z-index`
Controla el orden de apilamiento cuando sus reglas son aplicables.