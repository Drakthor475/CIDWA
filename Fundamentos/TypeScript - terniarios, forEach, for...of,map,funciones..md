
## Terniarios
El **operador ternario** permite escribir una condición de manera más corta que un `if...else`. Es especialmente útil cuando tenemos **dos posibles resultados** y queremos asignar uno de ellos.
```ts
condición ? valorSiVerdadero : valorSiFalso;

```
>**¿Se cumple la condición? Si sí, toma el primer valor; si no, toma el segundo.*
const edad: number = 20;

Ejemplo:
```ts
const mensaje: string = edad >= 18
    ? "Es mayor de edad"
    : "Es menor de edad";

console.log(mensaje);
```

## forEach()

`forEach()` es un método de los arreglos que permite recorrer cada  
elemento y ejecutar una función para cada uno.

### Sintaxis

```ts
arreglo.forEach((elemento) => {
    // código que se ejecuta por cada elemento
});
```

También podemos obtener el índice:

```ts
arreglo.forEach((elemento, indice) => {
    // código
});
```

### Ejemplo

```ts
const numeros: number[] = [10, 20, 30, 40];

numeros.forEach((numero) => {
    console.log(numero);
});
```

Resultado:

```ts
10
20
30
40
```

En cada iteración, `numero` representa el elemento actual.

### forEach() con índice

```ts
const nombres: string[] = ["Ana", "Luis", "Carlos"];

nombres.forEach((nombre, indice) => {
    console.log(indice, nombre);
});
```

Resultado:

```ts
0 Ana
1 Luis
2 Carlos
```

- `nombre` → valor actual.
- `indice` → posición del elemento.

### ¿Cuándo usar forEach()?

Es útil cuando:

- Queremos recorrer todos los elementos.
- Queremos ejecutar una acción para cada elemento.
- No necesitamos detener el recorrido antes de tiempo.
- No necesitamos crear un nuevo arreglo a partir del recorrido.

Ejemplo:

```ts
const alumnos: string[] = ["Ana", "Luis", "Carlos"];

alumnos.forEach((alumno) => {
    console.log(`Alumno: ${alumno}`);
});
```

### break y continue en forEach()

`forEach()` no permite utilizar `break` o `continue` directamente para  
controlar el recorrido.

No debemos hacer:

```ts
numeros.forEach((numero) => {
    if (numero === 10) {
        break;
    }
});
```

Si necesitamos detener el ciclo con `break` o saltar una iteración con  
`continue`, es mejor utilizar `for` o `for...of`.

---

## for...of

`for...of` permite recorrer directamente los valores de un elemento  
iterable, como un arreglo.

### Sintaxis

```ts
for (const elemento of arreglo) {
    // código
}
```

### Ejemplo

```ts
const numeros: number[] = [10, 20, 30, 40];

for (const numero of numeros) {
    console.log(numero);
}
```

Resultado:

```ts
10
20
30
40
```

Aquí `numero` representa directamente el valor.

### for tradicional vs for...of

Con `for` tradicional:

```ts
const numeros: number[] = [10, 20, 30];

for (let i = 0; i < numeros.length; i++) {
    console.log(numeros[i]);
}
```

Necesitamos utilizar el índice:

```ts
numeros[i]
```

Con `for...of`:

```ts
for (const numero of numeros) {
    console.log(numero);
}
```

Obtenemos directamente el valor.

### ¿Cuándo usar for...of?

Es recomendable cuando:

- Solo necesitamos los valores.
- Queremos un código sencillo de leer.
- Necesitamos utilizar `break`.
- Necesitamos utilizar `continue`.

### Ejemplo con continue

```ts
const numeros: number[] = [1, 2, 3, 4, 5, 6];

for (const numero of numeros) {

    if (numero % 2 !== 0) {
        continue;
    }

    console.log(numero);
}
```

Resultado:

```ts
2
4
6
```

`continue` ignora los números impares y pasa a la siguiente iteración.

### Ejemplo con break

```ts
const numeros: number[] = [3, 8, 12, 6, 20, 15];

for (const numero of numeros) {

    if (numero === 6) {
        console.log("Número encontrado");
        break;
    }
}
```

El ciclo termina cuando encuentra el `6`.

---
## map()

`map()` es un método de los arreglos que permite **recorrer cada elemento y crear un nuevo arreglo a partir de ellos**.

La diferencia fundamental con `forEach()` es:

```text
forEach()
    ↓
Recorre elementos y ejecuta una acción
    ↓
No crea un nuevo arreglo automáticamente


map()
    ↓
Recorre elementos y transforma cada uno
    ↓
Devuelve un nuevo arreglo
```

### Sintaxis

```ts
const nuevoArreglo = arreglo.map((elemento) => {
    return nuevoValor;
});
```

La función que recibe `map()` se ejecuta una vez por cada elemento.

---

### Ejemplo básico

```ts
const numeros: number[] = [1, 2, 3, 4];

const dobles: number[] = numeros.map((numero) => {
    return numero * 2;
});

console.log(dobles);
```

Resultado:

```text
[2, 4, 6, 8]
```

Podemos visualizarlo así:

```text
Arreglo original

[1, 2, 3, 4]
 ↓  ↓  ↓  ↓
map()
 ↓  ↓  ↓  ↓
[2, 4, 6, 8]

Arreglo nuevo
```

Cada elemento se transforma:

```text
1 → 1 × 2 → 2
2 → 2 × 2 → 4
3 → 3 × 2 → 6
4 → 4 × 2 → 8
```

---

## ¿Por qué se utiliza map()?

Se utiliza principalmente cuando queremos **transformar los elementos de un arreglo y obtener otro arreglo con los resultados**.

Por ejemplo, tenemos nombres:

```ts
const nombres: string[] = [
    "Ana",
    "Luis",
    "Carlos"
];
```

Podemos transformar cada nombre:

```ts
const nombresMayusculas: string[] = nombres.map((nombre) => {
    return nombre.toUpperCase();
});

console.log(nombresMayusculas);
```

Resultado:

```text
["ANA", "LUIS", "CARLOS"]
```

El arreglo original no cambia:

```text
nombres
    ↓
["Ana", "Luis", "Carlos"]

        map()

        ↓

nombresMayusculas
    ↓
["ANA", "LUIS", "CARLOS"]
```

---

## map() con objetos

`map()` es especialmente útil cuando trabajamos con arreglos de objetos.

Por ejemplo:

```ts
const alumnos = [
    {
        nombre: "Ana",
        edad: 20
    },
    {
        nombre: "Luis",
        edad: 22
    },
    {
        nombre: "Carlos",
        edad: 19
    }
];
```

Podemos obtener solamente los nombres:

```ts
const nombres: string[] = alumnos.map((alumno) => {
    return alumno.nombre;
});

console.log(nombres);
```

Resultado:

```text
["Ana", "Luis", "Carlos"]
```

Aquí `map()` transforma:

```text
Objeto alumno
      ↓
alumno.nombre
      ↓
String
```

Por lo tanto, el nuevo arreglo ya no contiene objetos, sino strings.

---

## map() para agregar información

También podemos crear nuevos objetos a partir de los existentes.

```ts
const alumnos = [
    {
        nombre: "Ana",
        edad: 20
    },
    {
        nombre: "Luis",
        edad: 22
    }
];

const alumnosConEstado = alumnos.map((alumno) => {
    return {
        nombre: alumno.nombre,
        edad: alumno.edad,
        activo: true
    };
});
```

Resultado:

```ts
[
    {
        nombre: "Ana",
        edad: 20,
        activo: true
    },
    {
        nombre: "Luis",
        edad: 22,
        activo: true
    }
]
```

Aquí cada objeto original se transforma en un nuevo objeto.

---

## map() con índice

Al igual que `forEach()`, `map()` puede recibir el índice:

```ts
const nombres = ["Ana", "Luis", "Carlos"];

const resultado = nombres.map((nombre, indice) => {
    return `${indice + 1}. ${nombre}`;
});

console.log(resultado);
```

Resultado:

```text
[
    "1. Ana",
    "2. Luis",
    "3. Carlos"
]
```

Los parámetros disponibles son:

```ts
(elemento, indice, arreglo)
```

Por ejemplo:

```ts
nombres.map((nombre, indice, arreglo) => {
    // código
});
```

---

## map() y return

Para que `map()` pueda construir el nuevo arreglo, debemos devolver el valor que queremos colocar en cada posición.

```ts
const numeros = [1, 2, 3];

const dobles = numeros.map((numero) => {
    return numero * 2;
});
```

El `return` indica qué elemento tendrá el nuevo arreglo.

```text
1 → return 2
2 → return 4
3 → return 6

Nuevo arreglo:

[2, 4, 6]
```

Si no devolvemos nada:

```ts
const dobles = numeros.map((numero) => {
    console.log(numero);
});
```

el resultado será:

```ts
[undefined, undefined, undefined]
```

Por eso `map()` debe utilizarse cuando realmente queremos **transformar cada elemento**.

---

## Retorno implícito

Como `map()` utiliza frecuentemente funciones flecha, podemos escribirlo de manera más corta.

Forma completa:

```ts
const dobles = numeros.map((numero) => {
    return numero * 2;
});
```

Forma corta:

```ts
const dobles = numeros.map(numero => numero * 2);
```

Ambas producen:

```text
[2, 4, 6]
```

La segunda utiliza un **retorno implícito**.

---

## Diferencia entre forEach() y map()

Esta es una diferencia fundamental:

### forEach()

```ts
const numeros = [1, 2, 3];

numeros.forEach((numero) => {
    console.log(numero * 2);
});
```

`forEach()` ejecuta una acción para cada elemento.

No necesitamos crear un nuevo arreglo.

---

### map()

```ts
const numeros = [1, 2, 3];

const dobles = numeros.map((numero) => {
    return numero * 2;
});
```

`map()` transforma cada elemento y **devuelve un nuevo arreglo**.

```text
forEach()

[1, 2, 3]
   ↓
ejecutar acción
   ↓
sin nuevo arreglo


map()

[1, 2, 3]
   ↓
transformar
   ↓
[2, 4, 6]
```

---

## ¿Cuándo utilizar cada uno?

### Usa forEach() cuando:

Quieres ejecutar una acción para cada elemento.

```ts
const nombres = ["Ana", "Luis", "Carlos"];

nombres.forEach((nombre) => {
    console.log(`Hola ${nombre}`);
});
```

---

### Usa map() cuando:

Quieres transformar cada elemento y obtener un nuevo arreglo.

```ts
const numeros = [1, 2, 3];

const cuadrados = numeros.map((numero) => {
    return numero * numero;
});
```

Resultado:

```text
[1, 4, 9]
```

---

## Regla sencilla

> **`forEach()` hace algo con cada elemento.**

> **`map()` transforma cada elemento y devuelve un nuevo arreglo.**

Por ejemplo:

```ts
const numeros = [1, 2, 3, 4];

numeros.forEach(numero => {
    console.log(numero);
});
```

Aquí solamente estamos recorriendo y realizando una acción.

En cambio:

```ts
const dobles = numeros.map(numero => numero * 2);
```

Aquí estamos transformando los datos y obteniendo:

```text
[2, 4, 6, 8]
```

---

## Comparación rápida

| Método | Recorre | Devuelve un nuevo arreglo | Uso principal |
|---|---|---|---|
| `forEach()` | Cada elemento | ❌ | Ejecutar una acción |
| `map()` | Cada elemento | ✅ | Transformar elementos |
| `for...of` | Cada valor | ❌ | Recorrer con control |
| `for` | Mediante índice | ❌ | Control preciso del ciclo |

### Idea clave

```text
forEach()
    ↓
"Quiero hacer algo por cada elemento"

map()
    ↓
"Quiero transformar cada elemento
y obtener un nuevo arreglo"
```
---
# Funciones en TypeScript

Una función es un bloque de código que realiza una tarea específica y  
puede recibir información y devolver un resultado.

Las funciones permiten:

- Reutilizar código.
- Organizar el programa.
- Evitar repetir instrucciones.
- Recibir datos mediante parámetros.
- Devolver resultados.

## Declarar una función

### Sintaxis

```ts
function nombreFuncion() {
    // código
}
```

### Ejemplo

```ts
function saludar() {
    console.log("Hola");
}
```

Para ejecutar la función:

```ts
saludar();
```

Resultado:

```ts
Hola
```

---

## Funciones con parámetros

Los parámetros permiten enviar información a una función.

```ts
function saludar(nombre: string) {
    console.log(`Hola ${nombre}`);
}
```

Uso:

```ts
saludar("Ana");
saludar("Luis");
```

Resultado:

```ts
Hola Ana
Hola Luis
```

En:

```ts
function saludar(nombre: string)
```

- `nombre` → parámetro.
- `string` → tipo del parámetro.

---

## Funciones con varios parámetros

```ts
function sumar(a: number, b: number) {
    console.log(a + b);
}
```

Uso:

```ts
sumar(10, 5);
```

Resultado:

```ts
15
```

Los valores enviados al llamar la función se conocen como  
**argumentos**.

```ts
sumar(10, 5);
     ↑   ↑
   argumento
```

---

## Funciones que devuelven un valor

Una función puede devolver un resultado utilizando `return`.

```ts
function sumar(a: number, b: number): number {
    return a + b;
}
```

La parte:

```ts
: number
```

indica que la función devuelve un número.

Podemos guardar el resultado:

```ts
const resultado: number = sumar(10, 5);

console.log(resultado);
```

Resultado:

```ts
15
```

### return

`return`:

- Devuelve un valor.
- Termina la ejecución de la función.

Ejemplo:

```ts
function obtenerEdad(): number {
    return 20;
}
```

---

## Funciones con condiciones

```ts
function esPar(numero: number): boolean {

    if (numero % 2 === 0) {
        return true;
    }

    return false;
}
```

Uso:

```ts
console.log(esPar(6)); // true
console.log(esPar(7)); // false
```

Una versión más corta:

```ts
function esPar(numero: number): boolean {
    return numero % 2 === 0;
}
```

---

## Funciones con arreglos

Podemos pasar un arreglo como parámetro.

```ts
function mostrarNumeros(numeros: number[]) {

    for (const numero of numeros) {
        console.log(numero);
    }

}
```

Uso:

```ts
const numeros: number[] = [10, 20, 30];

mostrarNumeros(numeros);
```

También podemos utilizar `forEach()`:

```ts
function mostrarNombres(nombres: string[]) {

    nombres.forEach((nombre) => {
        console.log(nombre);
    });

}
```

---

# Funciones flecha

Una **función flecha** (_arrow function_) es una forma alternativa y  
generalmente más compacta de definir una función en TypeScript y  
JavaScript.

Se llama función flecha porque utiliza el operador:

```ts
=>
```

### Función tradicional

```ts
function sumar(a: number, b: number): number {
    return a + b;
}
```

### Función flecha

```ts
const sumar = (a: number, b: number): number => {
    return a + b;
};
```

Ambas son funciones que reciben dos números y devuelven un número.

La diferencia principal en la sintaxis es que la función flecha se  
asigna normalmente a una variable o constante:

```ts
const sumar = (...) => {
    // código
};
```

---

## ¿Por qué se utilizan las funciones flecha?

Son especialmente útiles cuando necesitamos crear funciones pequeñas que  
vamos a pasar como argumento a otra función.

Esto ocurre mucho con métodos de arreglos como:

```ts
forEach()
map()
filter()
find()
reduce()
```

Por ejemplo:

```ts
const numeros: number[] = [1, 2, 3, 4];

numeros.forEach((numero) => {
    console.log(numero);
});
```

La parte:

```ts
(numero) => {
    console.log(numero);
}
```

es una función flecha que se entrega como argumento a `forEach()`.

Podríamos crear una función separada:

```ts
function mostrar(numero: number) {
    console.log(numero);
}

numeros.forEach(mostrar);
```

Pero si solamente se necesita para esa operación, puede ser más práctico  
escribirla directamente:

```ts
numeros.forEach((numero) => {
    console.log(numero);
});
```

---

## ¿Qué hace diferente a una función flecha?

Además de su sintaxis compacta, las funciones flecha tienen un  
comportamiento diferente respecto a `this`.

Una función tradicional puede tener su propio contexto de `this`  
dependiendo de cómo se invoque:

```ts
const persona = {
    nombre: "Ana",

    saludar() {
        console.log(this.nombre);
    }
};

persona.saludar();
```

Aquí `this` hace referencia al objeto `persona`.

Una función flecha **no crea su propio `this`**. Utiliza el `this` del  
contexto en el que fue creada.

Por eso no debemos reemplazar automáticamente todos los métodos de  
objetos o clases por funciones flecha.

Para una introducción a TypeScript, lo importante es recordar:

> Una función flecha es una forma compacta de definir funciones. Es  
> especialmente útil para funciones pequeñas y para pasarlas como  
> argumentos a otros métodos.

---

## Sintaxis de una función flecha

```ts
const nombreFuncion = (parametros) => {
    // código
};
```

Ejemplo:

```ts
const saludar = (nombre: string) => {
    console.log(`Hola ${nombre}`);
};
```

Uso:

```
saludar("Ana");
```

Resultado:

```
Hola Ana
```

---

## Función flecha con retorno

```ts
const sumar = (a: number, b: number): number => {
    return a + b;
};
```

Uso:

```
const resultado = sumar(10, 5);

console.log(resultado);
```

Resultado:

```
15
```

---

## Retorno implícito

Cuando una función flecha solamente devuelve una expresión, podemos  
eliminar las llaves y el `return`:

```ts
const sumar = (a: number, b: number): number => a + b;
```

Es equivalente a:

```ts
const sumar = (a: number, b: number): number => {
    return a + b;
};
```

La primera utiliza **retorno implícito**.

---

## Parámetros opcionales

Podemos indicar que un parámetro es opcional utilizando `?`.

```ts
function saludar(nombre: string, edad?: number) {
    console.log(`Hola ${nombre}`);
}
```

Puede utilizarse:

```
saludar("Ana");
```

o:

```
saludar("Ana", 20);
```

---

## Parámetros con valores por defecto

También podemos establecer un valor predeterminado:

```ts
function saludar(nombre: string = "Usuario") {
    console.log(`Hola ${nombre}`);
}
```

Si hacemos:

```ts
saludar();
```

Resultado:

```ts
Hola Usuario
```

Si hacemos:

```ts
saludar("Ana");
```

Resultado:

```ts
Hola Ana
```

---

## Funciones como parámetros

Una función puede recibir otra función como argumento.

Esto es precisamente lo que ocurre con `forEach()`:

```ts
const numeros: number[] = [1, 2, 3];

numeros.forEach((numero) => {
    console.log(numero);
});
```

Aquí:

```ts
(numero) => {
    console.log(numero);
}
```

es una función que se pasa como argumento a `forEach()`.

Conceptualmente:

```ts
forEach()
   │
   └── recibe una función
             │
             ▼
       (numero) => {
           console.log(numero);
       }
```

---

