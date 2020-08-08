---
title: Javascript - Trucos para javascript
description: Consejos para usar javascript de manera limpia
categories: 
  - Blog
  - Javascript
comments: true
---

{% comment %}
https://medium.com/swlh/javascripts-magical-tips-every-developer-should-remember-38c71b1cbfba
{% endcomment %}

**1.** Use `var` al crear una nueva variable. Siempre que esté creando una nueva variable, tenga en cuenta el uso de `var` delante del nombre de la variable, a menos que desee crear una variable global. Si crea una variable sin usar `var`, su alcance será automáticamente global, lo que a veces crea problemas, a menos que sea necesario.

También existe la opción de usar `let` y `const` dependiendo del caso de uso.

La instrucción `let` permite crear una variable con el alcance limitado al bloque en el que se utiliza.

Considere el siguiente fragmento de código.

```javascript
function varDeclaration(){
    let a =10;
    console.log(a);  // output 10
    if(true){
        let a=20;
        console.log(a); // output 20
    }
    console.log(a);  // output 10
}
```

Es el mismo comportamiento que vemos en la mayoría de los lenguajes.

```javascript
function varDeclaration(){
    let a =10;
    let a =20; //throws syntax error
    console.log(a);
}
```
**Error Message: Uncaught SyntaxError: Identifier ‘a’ has already been declared.**

Sin embargo, con `var`, funciona bien.

```javascript
function varDeclaration(){
    var a =10;
    var a =20;
    console.log(a);  //output 20
}
```

El alcance se mantendrá bien con una declaración `let` y cuando se utiliza una función interna, la declaración `let` hace que su código sea limpio y claro.

Los valores de la sentencia `const` pueden asignarse una vez y no pueden reasignarse. El alcance de la declaración `const` funciona de manera similar a las declaraciones `let`.

```javascript
function varDeclaration(){
    const MY_VARIABLE =10;
    console.log(MY_VARIABLE);  //output 10
}
```

Pregunta: ¿Qué sucederá cuando intentemos reasignar la variable `const`?

Considere el siguiente fragmento de código.

```javascript
function varDeclaration(){
    const MY_VARIABLE =10;
    console.log(MY_VARIABLE);  //output 10
    MY_VARIABLE =20;           //throws type error
    console.log(MY_VARIABLE);
}
```

**Error Message : Uncaught TypeError: Assignment to constant variable.**

El código arrojará un error cuando intentemos reasignar la variable `const` existente.

**2.** Utilice siempre `===` como comparador en lugar de `==` (estricto igual). Use `===` en lugar de `==` porque cuando usa `==` hay una conversión automática de tipos involucrada que puede conducir a resultados no deseados.

```javascript
3 == ‘3’ // true
3 === ‘3’ //false
```

Esto sucede porque en `===` la comparación tiene lugar entre el valor y el tipo.

```javascript
[10] == 10   // is true
[10] === 10  // is false
'10' == 10   // is true
'10' === 10  // is false
[] == 0      // is true
[] === 0     // is false
'' == false  // is true
'' === false // is false
```

**3.** `undefined`, `null`, `0`, `false`, `NaN`, (cadena vacía) son todas condiciones falsas.

**4.** Vaciar una matriz

```javascript
var sampleArray = [2, 223, 54, 31];
sampleArray.length = 0; // sampleArray becomes []
```

**5.** Redondeo a N decimales

```javascript
var n = 2.4134213123;
n = n.toFixed(4); // computes n = "2.4134"
```

**6.** Verifique que su cálculo produzca un resultado finito.

```javascript
isFinite(0/0);       // false
isFinite('foo');     // true
isFinite('10');      // true
isFinite(10);        // true
isFinite(undefined); // false
isFinite();          // false
isFinite(null);      // true
```

Tomemos un ejemplo para comprender el uso de esta función, supongamos que ha escrito una consulta de base de datos sobre una tabla que contiene una gran cantidad de datos y después de la ejecución de la consulta no está seguro de todos los valores de resultado posibles de esa consulta. Los datos de la consulta cambian en algo que usted pone dinámicamente en la consulta. En tal caso, no está seguro acerca de la propiedad finita del resultado y si usa ese resultado directamente, puede darle una condición infinita, lo que puede romper su código.

Por lo tanto, se recomienda usar `isFinite()` antes de cualquiera de estas operaciones para que los valores infinitos se puedan manejar correctamente.

**7.** Use una instrucción `switch/case` en lugar de una serie de `if/else`

Usar `switch/case` es más rápido cuando hay más de 2 casos, y es más elegante (código mejor organizado). Evite usarlo cuando tenga más de 10 casos.

**8.** Uso de `use strict”` dentro de su archivo. La cadena `use strict”` evitará que se preocupe por la declaración de una variable que mencioné en el primer punto.

```javascript
// This is bad, since you do create a global without having anyone to tell you
(function () {
   a = 42;
   console.log(a);
   // → 42
})();
console.log(a);
// → 42
```

`use strict` lo mantendrá alejado de cometer el anterior error. Usando `use strict`, puede obtener bastantes errores:

```javascript
(function () {
   “use strict”;
   a = 42;
   // Error: Uncaught ReferenceError: a is not defined
})();
```

Podría preguntarse por qué no puede poner `use strict`fuera de la función de envoltura. Bueno, puedes, pero se aplicará globalmente. Eso no está mal del todo; pero afectará si tiene código que proviene de otras bibliotecas, o si agrupa todo en un archivo.

**9.** Use `&&` y `||` para crear magia

```javascript
“” || “foo”
// -> “foo”undefined || 42
// -> 42function doSomething () {
   return { foo: “bar” };
}
var expr = true;
var res = expr && doSomething();
res && console.log(res);
// -> { foo: “bar” }
```

Además, no olvide usar un embellecedor de código al codificar. Utilice JSLint y minificación (JSMin, por ejemplo) antes de lanzarlo. Esto lo ayudará a mantener un estándar de codificación en su proyecto y hacerlo lo más estándar posible.


### Contacto

- Envia tus comentarios al correo `henrytorrespo@yahoo.com`
