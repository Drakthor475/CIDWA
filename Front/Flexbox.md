Es una herramienta de CSS que permite distribuir, alinear y espaciar elementos dentro de un contenedor.
## ¿Qué problema resuelve Flexbox?

Imagina que tienes tres tarjetas de cursos. Sin un sistema de distribución adecuado, podrías terminar ajustando márgenes y posiciones manualmente para conseguir que queden alineadas.

**Flexbox permite controlar esa distribución desde el contenedor padre.  

![[Pasted image 20261014183906.png]]

La diferencia principal es que Flexbox permite controlar la relación entre varios elementos sin tener que posicionar cada uno por separado.
## Concepto padre e hijos

Para utilizar Flexbox, normalmente defines un contenedor padre y colocas dentro los elementos que deseas organizar.

```html
<div class="contenedor-cursos">
  <div class="curso">HTML y CSS</div>
  <div class="curso">JavaScript</div>
  <div class="curso">TypeScript</div>
</div>
```

La propiedad `display: flex` se aplica al padre, no a cada tarjeta.

- Contenedor flex: el elemento que tiene `display: flex`.
    
- Elementos flex: los hijos directos del contenedor.
    
- Eje principal: la dirección en la que se distribuyen los elementos.
    
- Eje transversal: la dirección perpendicular al eje principal.

### `flex-direction`: elegir la dirección
Esta propiedad determina la dirección del eje principal.

### `flex-direction: column`

Los elementos se colocan verticalmente, uno debajo del otro.
Ejemplo: opciones de un menú lateral.

### `flex-direction: row`

Los elementos se colocan horizontalmente. Es el valor predeterminado.


![[Pasted image 20261014184207.png]]

También existen `row-reverse` y `column-reverse`, que invierten el orden visual.

### `justify-content`: distribuir sobre el eje principal

Esta propiedad controla cómo se distribuye el espacio libre entre los elementos en el eje principal.
alor

#### Valores de `justify-content`
| Valor           | ¿Qué hace?                                                                    |
| --------------- | ----------------------------------------------------------------------------- |
| `flex-start`    | Coloca los elementos al inicio del eje principal.                             |
| `flex-end`      | Coloca los elementos al final del eje principal.                              |
| `center`        | Agrupa los elementos en el centro del eje principal.                          |
| `space-between` | Distribuye el espacio libre entre los elementos, sin añadirlo a los extremos. |
| `space-around`  | Reparte el espacio alrededor de cada elemento.                                |
| `space-evenly`  | Reparte el espacio libre por igual entre elementos y extremos.                |

### `align-items`: alinear sobre el eje transversal

Mientras `justify-content` distribuye sobre el eje principal, `align-items` controla la alineación sobre el eje transversal.

#### Valores de align-items
| Valor        | ¿Qué hace?                                                                                                                                |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `stretch`    | Estira los elementos para ocupar el espacio transversal disponible, si no tienen una dimensión que lo impida. Es el valor predeterminado. |
| `flex-start` | Alinea los elementos al inicio del eje transversal.                                                                                       |
| `flex-end`   | Alinea los elementos al final del eje transversal.                                                                                        |
| `center`     | Centra los elementos en el eje transversal.                                                                                               |
| `baseline`   | Alinea los elementos por la línea base del texto.                                                                                         |
## CSS Flexbox: `gap`, `flex-wrap` y `nowrap`

Estas tres propiedades ayudan a controlar la separación entre elementos y qué sucede cuando no caben en una misma fila.

### `gap`: separación entre elementos

La propiedad `gap` establece el espacio entre los elementos de un contenedor Flexbox. No agrega espacio exterior alrededor de todo el contenedor, sino entre los elementos.
```css
.cursos {
  display: flex;
  gap: 20px;
}
```

También puedes especificar separaciones diferentes para filas y columnas:

```css
.cursos {
  display: flex;
  flex-wrap: wrap;
  column-gap: 24px;
  row-gap: 16px;
}
```

- `column-gap`: espacio entre elementos en la dirección de las columnas.
- `row-gap`: espacio entre filas cuando los elementos se distribuyen en varias líneas.
- `gap: 16px 24px`: establece `16px` entre filas y `24px` entre columnas

### `flex-wrap`: permitir que los elementos pasen a otra línea

Por defecto, Flexbox intenta mantener todos los elementos en una misma línea. La propiedad `flex-wrap` permite cambiar ese comportamiento.

|Valor|Comportamiento|
|---|---|
|`nowrap`|Mantiene los elementos en una sola línea. Es el valor predeterminado.|
|`wrap`|Permite que los elementos pasen a otra línea si no hay espacio suficiente.|
|`wrap-reverse`|Permite varias líneas, pero invierte su orden en el eje transversal.|

### `flex-wrap: nowrap`

Los elementos permanecen en una sola línea. Si no caben, Flexbox puede reducir sus dimensiones cuando sea posible. Si no pueden reducirse lo suficiente, pueden desbordarse del contenedor.

![[Pasted image 20261014190123.png]]

### `flex-wrap: wrap`

Los elementos pasan a otra línea cuando ya no caben en la línea actual, teniendo en cuenta sus dimensiones y el espacio disponible

![[Pasted image 20261014190237.png]]

## Flex items

Los Flex Items son los elementos hijos directos de un contenedor que tiene `display: flex`. Para controlarlos individualmente, CSS ofrece varias propiedades que determinan cuánto crecen, cuánto se encogen, qué tamaño tienen y cómo se alinean.

### Propiedades principales de los Flex Items

| Propiedad     | ¿Para qué sirve?                                                                               | Ejemplo               |
| ------------- | ---------------------------------------------------------------------------------------------- | --------------------- |
| `flex-grow`   | Define cuánto puede crecer el elemento para ocupar espacio libre.                              | `flex-grow: 1;`       |
| `flex-shrink` | Define cuánto puede encogerse si falta espacio.                                                | `flex-shrink: 1;`     |
| `flex-basis`  | Define el tamaño inicial del elemento antes de distribuir el espacio disponible.               | `flex-basis: 200px;`  |
| `flex`        | Atajo para establecer `flex-grow`, `flex-shrink` y `flex-basis`.                               | `flex: 1 1 200px;`    |
| `align-self`  | Sobrescribe la alineación transversal que establece `align-items` para un elemento específico. | `align-self: center;` |
| `order`       | Cambia el orden visual del elemento dentro del contenedor flex.                                | `order: 2;`           |
