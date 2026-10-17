TypeScript comparte la misma sintaxis que Javascript solo que es una sintaxis para tipos.
JavaScript es un lenguaje  de tipado dinamico.
Javascrip es el lenguaje nativo que entienden los navegadores y TS añade orden seguridad y escabilidad.
**EL NAVEGADOR NUNCA LEERA TS.**
## Variables,tipado dinamico e impresión de datos.
Existen tipos de datos primitivos en Ts como en C++ los datos primitivos son los siguiente.
* string
* number
* boolean
* null
* undefined 
### ¿Pero como declaro estas variables?
La forma de declarar variables es la siguiente:
```ts
let nombre: string = 'Cante'
```
donde **let** es una palabra clave de TS Y JS  que se utiliza para declarar variables, seguido a eso viene el nombre de nuestra variable como la vamos a identificar , posteriormente el tipo que es y el valor que le vamos a asignar a esa variable.
#### let, const y var 
Para declarar una variable en TS se utilizan estas palabras claves las cuales se  ocupan en diferentes situaciones.

* **let** declara una variable cuyo valor puede cambiar o ser reasignado mas adelante del código.
* **const** declara una constante cuyo valor no se puede cambiar cambiar o reasignar después de su inicialización.
* **var** era la forma antigua de declarar variables.
### Tipado dinamico 
Una de las ventajas principales de TS es que no es necesario especificar el tipo de dato como en C++ , TS puede inferir el tipo de dato sin haberlo especificado:
```ts
let nombre='CANTE'
```
Directamente TS infiere que nuestra variable nombre es de tipo string sin la necesidad de de especificarselo.
#### ¿Que diferencia TS a JS?
La principal diferencia  de TS con respecto a JS es que TS es de tipado fuerte y que cuando especificamos lso tipos estos no apareceran en JS. 

```js
let nombre= 'cante'
nombre=3
```
JS permitara asignar el nuevo valor a la variable sin portar el tipo que habia declarado antes.
```ts
let nombre= 'cante'
nombre=3
```
 TS indentificara que el nuevo valor es de diferente tipo y no lo podra asignar.
**Todo codigo de TS se traducira a JS y si se especifico un tipo de dato este no aparecera.**
### ¿Como imprimo información?

En TS y JS para imprimir información es por medio de consola, se ocupa la palabra clave **console.log.**
```ts
console.log('Texto')
console.log(3)
console.log(nombre)
console.log(3+2)
console.log(`Hola , mi nombre es ${nombre}`);
```

## Condicionales 
Los condicionales permiten que un programa tome deciciones. 
En TS y JS las condiciones se manejan de la misma forma que en C++.

```ts
const edad=20;
if(edad===20){
	console.log(`Tu edad es de ${edad}`)
}
```
La idea es exactamente la misma, si se cumpla cierta condicion se ejecuta ciertas instrucciones si no otras.
### Operadores
|Operador|Significado|Ejemplo|
|---|---|---|
|`===`|Igual a|`edad === 18`|
|`!==`|Diferente de|`edad !== 18`|
|`>`|Mayor que|`edad > 18`|
|`<`|Menor que|`edad < 18`|
|`>=`|Mayor o igual|`edad >= 18`|
|`<=`|Menor o igual|`edad <= 18`|
**En TS  el operador = sirve para asignar valores para comparar se ocupan ===**

## CICLOS
En TS igual que en C++ existen ciclos. 
Los ciclos permiten repetir un bloque de código varias veces sin tener que escribirlo manualmente.
La estructura basica es:
```ts
for(inicialización;condición;actualización){
	//Codigo que se repite 
}
```
 Un ejemplo 
```ts
for(let i=0;i<5;i++){
	console.log(i);
}
```
Esto imprime los numeros 0 1 2 3 4 
Es posible cambiar el incremento por ejemplo podemos aumentar de 2 en 2 de la siguiente forma:
 
```ts
for(let i=0;i<=10;i += 2){
	console.log(i);
}
```

O también podemos  podemos contar hacia atrás.
```ts
for(let i=5;i>=0;i--){
	console.log(i);
}
```
## Arreglos 
Un arreglo es una estructura que permite almacenar varios valores dentro de una misma variable. 
En lugar de hacer 
```ts
const alumno1: string = "Ana";
const alumno2: string = "Luis";
const alumno3: string = "Pedro";
```
podemos agruparlos en una sola variable :
```ts
const alumnos: string[] = ["Ana", "Luis", "Pedro"];
```

La forma de  declarar arreglos en TS 
```ts
const nombres: string[] = ["Ana", "Luis", "Pedro"];
```
### ¿Cómo accedemos a los elementos?
Los elementos de un arreglo tienen un índice.
Para acceder un elemento es:
```ts
const nombres: string[] = ["Ana", "Luis", "Pedro"];

console.log(nombres[0]);
```
Propiedades de los arreglos.
Los arreglos poseen ciertas propiedades y métodos, los cuales son los siguientes:
*  ***lenght*** -> es una propiedad muy importante que nos indica cuántos elementos tiene el arreglo.
```ts
const nombres: string[] = [
    "Ana",
    "Luis",
    "Pedro"
];

console.log(nombres.length);
```
*  ***push*** -> Push es un metodo que sirve para agregar uno o más elementos al final del arreglo.
```ts
const nombres: string[] = [
    "Ana",
    "Luis"
];

nombres.push("Pedro");
```
* ***pop*** -> Pop sirve para eliminar el último elemento.
```ts
const nombres: string[] = [
    "Ana",
    "Luis",
    "Pedro"
];

nombres.pop();
```
### ¿Como recorro un arreglo?
Una de las aplicaciones más importantes de `for` es recorrer arreglos.
```ts
const nombres: string[] = [
    "Ana",
    "Luis",
    "Pedro"
];
```

Esto es posible con:
```ts
for (let i = 0; i < nombres.length; i++) {
    console.log(nombres[i]);
}
```
## Break y Continue 
Cuando hablamos de ciclos tenemos que tomar en cuenta dos instrucciones muy Importantes.
### Break 
Sirve para terminar inmediatamente el ciclo 
```ts
for (let i = 0; i < 10; i++) {

    if (i === 5) {
        break;
    }

    console.log(i);
}
```
### Continue
A diferencia de break continue no termina el ciclo lo que que sucede es que salta la iteración actual y continua con la siguiente.
```ts
for (let i = 0; i < 5; i++) {

    if (i === 2) {
        continue;
    }

    console.log(i);
}
```

#### Ejercicio
* Buscar un numero dentro de un arreglo
* Imprimir solo los numero pares del 0 al 10 

## POO

Es un paradigma de programación que organiza un programa alrededor de objetos.
### ¿Pero que son los objetos?

>Un objeto es una representación o abstracción de una entidad del mundo real o
  conceptual dentro de un programa, que contiene características y comportamientos relacionados.
### ¿Como se ven en TS?
```ts
const alumno = {
    nombre: "Ana",
    edad: 20,
    carrera: "MAC",
    semestre: 5
};
```

### Objetos en el mundo real 

Una de las ideas centrales de la POO es que podemos **modelar elementos del mundo real dentro de un programa**.

Por ejemplo:
```
Mundo real                 Programa

Alumno                     objeto Alumno
   │                           │
   ├── nombre                  ├── nombre
   ├── edad                    ├── edad
   ├── carrera                 ├── carrera
   └── semestre                └── semestre
```
### Propiedades y comportamientos 
#### Propiedades 
Representan **información o características**.
```ts
const alumno = {
    nombre: "Ana",
    edad: 20,
    semestre: 5
};
```
#### Metodos 
Representan **acciones o comportamientos**.
```ts 
const alumno = {
    nombre: "Ana",
    edad: 20,

    saludar() {
        console.log("Hola");
    }
};
```
La idea fundamental:

> **Las propiedades representan lo que un objeto tiene y los métodos representan lo que un objeto puede hacer.**

### Como declaro objetos en TS
La forma de declarar objetos en TS es la sig:
```ts
const alumno = {
    nombre: "Ana",
    edad: 20,
    carrera: "MAC"
};
```
### Acceder a las propiedades.
Para acceder a las propiedades de un objeto se utiliza un ``.``
```ts
console.log(alumno.nombre);
console.log(alumno.edad);
console.log(alumno.carrera);
```
### Definir una variable de tipo objeto 
Para definir el tipo y estructura que tendrá una variable que almacena se utiliza:
```ts
type Alumno = {
    nombre: string;
    edad: number;
    carrera: string;
};
```

>`type` permite crear un tipo de objeto personalizado, indicando qué propiedades debe tener y qué tipo de dato almacena cada propiedad.

Entonces creamos una variable  de la siguiente forma:
```ts
const alumno1: Alumno={
nombre:"Cante",
edad:22, 
carrera:"MAC"
}
```

