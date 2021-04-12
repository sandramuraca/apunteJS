# APUNTES JS 📚

Este apunte fue realizado con material obtenido en:
- Clases curso Desarrollo Front End - ADA 7ma.
- Notas tomadas del curso de Corseit de JS
- Notas del curso de Udemy de Fernando Herrera - Programación para principiantes
- Paginas consultadas en la web.

## Objetivo🎯
Este apunte es un resumen de los conceptos principaes de JS, el A B C, para principiantes.
Para no perderse, ir ordenado y con ejemplos prácticos de algunos ejercicios.
La idea es ir actualizandolo, e incorporar nuevos conceptos a medida que los vaya viendo.

<a name="indice"></a>

## INDICE 📑
* [INTRO:](#intro)
- Que es JS?
- Características
- Formas de vincular HTML y JS

* [INSTRUCCIONES BÁSICAS:](#instrucciones)
- `console.log`
- `alert`

* [VARIABLES](#variables)
* [Como nombrar una variable?](#nombre_variable)
* [TIPOS DE DATOS](#tipo_dato)
    - Strings
    - Numbrer
    - Boolean
    - Undefined
    - Null
    - Nan
    - Que comillas usar?

* [CONCATENAR](#concat)
* [OPERADORES MATEMATICOS](#op_mat)
* [OBJETOS](#objetos)
* [ARRAYS](#arrays)
* [ESTRUCTURAS DE CONTROL](#control)
    - `if`
    - `else if`
    - `else`
    - `Operadores de comparación`
    - `Operadores Lógicos`

* [SWITCH](#switch)

* [FUNCIONES](#funciones)

* [DOM](#dom)
    - Selectores
    - Métodos
    - ClassList
    - Scope
    - Eventos
***
<a name="intro"></a>
# ¿Qué es JavaScript?

JavaScript se creó inicialmente para "dar vida a las páginas web". 
Existía un necesidad de generar *interacción* con el usuario.
Los *programas en este idioma se denominan scripts* . Pueden escribirse directamente en el `HTML` de una página web y ejecutarse automáticamente a medida que se carga la página.
Los scripts se proporcionan y ejecutan como texto sin formato. 
No necesitan preparación especial o compilación para ejecutarse.
Se lo considera un lenguaje de programación seguro. No proporciona acceso de bajo nivel a la memoria o la CPU, ya que se creó inicialmente para navegadores que no lo requieren.

## ¿Qué hace que JavaScript sea único?
Hay al menos tres cosas buenas sobre JavaScript:
- Integración completa con `HTML` / `CSS`.
- Las cosas sencillas se hacen de forma sencilla.
- Compatible con todos los navegadores principales y habilitado de forma predeterminada.

## Características:
- Débilmente tipado
- Interpretado
- Dinámico
- Secuencial: lee las instrucciones en orden de arriba hacia abajo.

## Formas de vincular HTML con JS:

1. Dentro de un archivo HTML una etiqueta <script> </script> indica un cambio de lenguaje, todo lo que esté dentro de ella estará en JS, se coloca dentro del body y 🚫 no se anidan 🚫.
~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script>
        //todo lo que se escriba aqui es JS
    </script>
</body>
</html>
~~~
2. Tambien se puede linkear el index.html con un archivo app.js externo mediante el atributo src.
El archivo app.js tiene que estar en la misma carpeta que el html, o si esta por fuera indicar la ruta que corresponda.

~~~
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
    <script src="app.js"></script>
    
</body>
</html>
~~~

<a name="instrucciones"></a>

### Todo lo que se escriba en JS puede leerse en la `consola`.
¿Cómo?
Abriendo el archivo HTML con live server, haciendo click derecho `Inspeccionar`:
![image](./img/consola.png)

¿Cómo escribí ese código en JS?
~~~
<script>
   console.log("hola! soy un string y quiero que me veas por la consola");
</script>
~~~
La instrucción 
~~~
console.log()
~~~
te permite ver lo que escribiste entre paréntesis (luego vemos qué tipo de dato es).

Y si no lo quiero ver en la consola?🤔
~~~
<script>
    alert("hola! soy un string y quiero que me veas por la consola");
</script>
~~~
La instrucción
~~~
alert()
~~~
muestra un mensaje en el browser:

![image](./img/alert.png)

Otra instrucción muy común es 
~~~
prompt, 
~~~
QUE HACE ❓
Abre un cuadro de diálogo con el usuario, donde le puedo hacer una pregunta, y su respuesta se convierte en un “dato”.
Pero el `prompt` no guarda el dato en ninguna parte, entonces... le haría una pregunta a un usuario y luego no podría utilizar ese dato que me dio en su respuesta?🤔

para eso vamos a utilizar las:
<a name="variables"></a>

### 🔴 VARIABLES
Ejemplo:
~~~
<script>
    prompt("cual es tu nombre?");
</script>
~~~
![image](./img/prompt.png)

En el ejemplo anterior si el usuario me responde su nombre, si no lo tengo almacenado en una `VARIABLE`, lo pierdo, entonces:
~~~
<script>
    prompt("cual es tu nombre?");
</script>
~~~
![image](./img/promptNombre.png)
Puedo verlo en la consola:
![image](./img/consolaNombre.png)

Para entender esto 👆 tenemos que entender lo que es una
🚩VARIABLE🚩

Es un *espacio de memoria* (como una cajita 📦) donde se almacenan distintos tipos de datos.

Siempre tiene un *nombre que las identifica* que debe ser único.

**Se las puede nombrar de 3 formas**:
* `var` : en desuso
* `let`: puede cambiar su valor (ejemplo del nombre, si entra otro usuario, el nombre va a ser otro).
* `const`: no puede cambiar su valor.

Declarar e inicializar una variable es asignarle: 
* *Nombre* (declarar)
* *Valor* (entiéndase valor al dato que va a guardar) -> (inicializar)

Ejemplo:
~~~
<script>
    let nombre = "Sandra";
</script>
~~~

En este caso el *nombre de la variable* es “nombre” y el valor es “Sandra”. 
Como se que el valor es ese? 
Porque con el `signo =` se le asignan valor a las variables, se lo llama *OPERADOR DE ASIGNACIÓN*.

Cada vez que se termina de declarar una sentencia para cerrarla se debe colocar un punto y coma ( ; ) ❗❗❗

Las variables se pueden declarar todas en una misma línea separadas por comas:
~~~
<script>
    let nombre = "Sandra"; edad= 42; nacionalidad = "argentina";
</script>
~~~

En este ejemplo hay 3 variables: nombre, edad, nacionalidad.
Y los valores son: “Sandra”, 42, “argentina”.

🤪 por que “Sandra” y “argentina” están entre comillas y 42 no???? 👀

Porque todo lo que es *TEXTO ó STRING va entre comillas*, lo que es *NÚMERO* no  ❗❗❗ y esto es así porque esos datos son de distinto *TIPO*.

<a name="nombre_variable"></a>

### 🔺 La importancia del nombre de la variables:
* Su nombre tiene que representar a los datos que almacena.
* Debe ser legibles por humanos.
* Evitar usar abreviaturas o letras sueltas.
* Tenga en cuenta las definiciones de su equipo de conceptos básicos y atengase a ellas, ejemplo: Usuario = user.
* Caracteres disponibles: letras del alfabeto, menos la ñ; números, $, guión bajo.
* No pueden iniciar con un número.
* JS tiene palabras reservadas que no se pueden utilizar para nombrar variables, ej: *if, for, function*.

### Formas de escribir una variable ✍:
* `camelCase`: primera letra en min y la primer letra de la segunda palabra en MAY.
* `snake_case`: palabras separadas por un guion bajo
* `PascalCase`: primer letra de la primer palabra en MAY y primer letra de la segunda palabra en MAY.

<a name="tipo_dato"></a>

## TIPOS DE DATOS 📊:

* `STRINGS` 📝: cadena de texto
~~~
<script>
    let texto = "Un String es una cadena de texto";
    let nombre = "Sandra";
</script>
~~~

* `NÚMEROS` :
~~~
<script>
    let edad = 42;
    let edad = "42"
</script>
~~~

El número va 👀SIEMPRE SIN COMILLAS👀, en el segundo caso lo interpreta como texto.

Los números pueden ser:

* Positivos
* Negativos
* Decimales
* Con ellos se pueden realizar operaciones matemáticas ➕➖➗✖

* `BOOLEAN`: valor “true” y “false”.✔❌
* `UNDEFINED`: indefinido, declarar una variable y no asignarle ningún valor.
~~~
<script>
    let nombre 
</script>
~~~
![image](./img/indefinido.png)

* `NULL`: nulo = valor especial que representa "nada", "vacío" o "valor desconocido.
* `NAN`: not a number, cuando queremos realizar una operación matemática con un dato que no es un número.

### COMILLAS PARA DECLARAR UNA VARIABLE:
Se pueden usar:
* comillas dobles: “ ”  let nombre = “Sandra”;
* comillas simples: ‘ ‘   let nombre = ‘Sandra’; (alt+39)
* backticks: let nombre = `Sandra`; (alt+96)
Las backticks se utilizan para una forma particular de *CONCATENAR*.

<a name="concat"></a>

### Que es CONCATENAR?:
Unir dos o más cadenas de texto y datos.
Se puede concatenar con el signo + (opción 1), o utilizando ` ` y ${} (opción2)
Ejemplo:

1. 
~~~
let nombre = "Sandra";
let apellido = "Muraca";
let edad = 42;
 
alert ("hola soy" + nombre + "" + apellido + "y tengo" + edad + "" + "soy argentina y estudio programación");
~~~

2. 
~~~
let nombre = "Sandra";
let apellido = "Muraca";
let edad = 42;
 
alert (`hola soy ${nombre} ${apellido}y tengo ${edad} soy argentina y estudio programación`);
~~~

El resultado de ambas opciones es el mismo:

![image](./img/tipoComillas.png)

<a name="op_mat"></a>

### OPERADORES MATEMÁTICOS ➕➖➗:
Para realizar operaciones matemáticas utilizamos los siguientes signos:

(+) SUMA
(-) RESTA
(/) DIVISIÓN
(*) MULTIPLICACIÓN
(%) RESTO

Existen otros operadores, como el de potenciación, decremento e incremento.

### Links a Ejercicios con los conceptos vistos 🏋️‍♀️:
* [Introducción a JS](https://github.com/sandramuraca/introduccionJS)
* [Variables, Datos, Operadores](https://github.com/sandramuraca/VARIABLES_OPERADORES_DATOS)

🔼 [VOLVER AL INDICE](#indice)
***
<a name="objetos"></a>
🚩OBJETOS🚩

En construcción 🔧🔨🛠⚙

<a name="arrays"></a>
🚩ARRAYS🚩

Es una lista de elementos, que  tienen relación entre sí. 
Se escriben entre corchetes [ ] → es un tipo de OBJETO.
Es una forma de agrupar elementos (de cualquier tipo).

Ejemplo:

Array FAMILY es el agrupamiento de las variables de cada integrante de la familia👇
~~~
const person1 = {
            name: `Sandra`,
            surname: `Muraca`,
            age: 42 
        };
 
        const person2 = {
            name: `Victoria`,
            surname: `Capella`,
            age: 13 
        };
 
        const person3 = {
            name: `Cristian`,
            surname: `Rodriguez`,
            age: 40
        };
 
        const family = [person1, person2, person3]
~~~

Los arrays tienen **“índices”** que es la posición de cada elemento que agrupa, el indice siempre arranca en 0.

Ejemplo:
~~~
console.log (family); // aca en el console muestra los 3 elementos con su nro indice
~~~
![image](./img/array.png)

El elemento 0 de este array es “Sandra” y así sucesivamente.

~~~
console.log (family[0]); // aca llamamos al elemento, con todos us componentes, indicado con el nro entre corchetes según el indice
~~~
![image](./img/array2.png)

Ese índice se utiliza para llamar a cualquiera de esos elementos desde la consola según su numeración.
En los arrays importa el orden de los elementos.
El potencial del arrays está con los **MÉTODOS** que viene por default con JS → son funcionalidades previamente programadas, el más utilizado es “push” →
nombreDeLaVariable.push()

~~~
 family.push({
            name: `gata`,
            surname: `flora`,
            age: 7
        }) 
        /// de esta manera se agregan elementos dinamicos al array
~~~

luego de haber agregado un elemeto más al array, se hacemos console.log:

![image](./img/array3.png)

<a name="control"></a>

### 🚩ESTRUCTURAS DE CONTROL🚩

* Podemos controlar el flujo del código y cómo queremos que se ejecute según se cumplan o no algunas condiciones.
* Se denominan *CONDICIONALES*:
    * `if`
    * `else if`
    * `else`

* **if**: (si entonces) espera una condición **true** para ejecutar el código, si es **false** las instrucciones no se ejecutan y el programa sigue su flujo.

~~~
 let numero = 2;
        if (numero >= 2) {
            alert("El numero es mayor o igual a 2");
        }

~~~
![image](./img/if.png)

* **else** (si no) permite controlar que pasa si la condición es falsa, no necesita ningún parámetro, por que se ejecuta cuando el parametro declarado en if es  false.

~~~
   let numero = 1;
        if (numero >= 2) {
            alert("El numero es mayor o igual a 2");
        } else {
            alert ("el número no es mayor o igual a 2");
        }
~~~
![image](./img/else.png)

* **else if** (si entonces si) en el tercer camino, es una contra condición.

~~~
// este es un condicional de mas de 2 caminos
        const age = 80;
 
        if (age >= 65) {
            console.log(`soy jubilado`);
        } else if (age >= 18 && age < 65){
            console.log(`soy mayor de edad`);
        } else {
            console.log(`soy menor de edad`);
        }
~~~

Con los **condicionales** se utilizan en los parámetros los **OPERADORES DE COMPARACIÓN**:

![image](./img/operadoreComparacion.png)

y también los **OPERADORES LÓGICOS**:

![image](./img/operadoresLogicos.png)

(|| operador barra vertical= alt + 124)

### DFD DE UNA ESTRUCTURA DE CONTROL DE 2 CAMINOS:
![image](./img/dfd.png)

💡 LOS CONDICIONALES PERMITEN TOMAR DECISIONES RESPECTO DE QUÉ CAMINO VA A TOMAR MI CODIGO SI PASA UNA COSA U OTRA.

<a name="switch"></a>

🚩SWITCH🚩

Forma de anidamiento de múltiples expresiones IF, ELSE IF, ELSE.
Su uso no siempre es necesario resulta útil para introducir eficiencia y claridad al código.
En su contenido se quiere evaluar. 
Ejemplo:
~~~
let diaDeLaSemana = Number(prompt ("Ingrese un número, le diremos a que dia de la semana corresponde"));
 
        switch (diaDeLaSemana) {
            case 1:
                alert ("Es lunes");
                break;
            case 2:
                alert ("Es martes");
                break;
            case 3:
                alert ("Es miercoles");
                break;
            case 4:
                alert ("Es jueves");
                break;
            case 5:
                alert ("Es Viernes");
                break;
            default:
                alert ("no ha ingresado un numero valido");
                break;
        }
~~~

El `default` es opcional, son las instrucciones que se ejecutan si no se verifican ninguno de los casos evaluados.

### Links a Ejercicios con los conceptos vistos 🏋️‍♀️:
* [Ejercitación Condicionales](https://github.com/sandramuraca/ejercicios_condicionales)

🔼 [VOLVER AL INDICE](#indice)

<a name="funciones"></a>

### 🔴 FUNCIONES:

Es un bloque de código **reutilizable** 🔄.
Tipos:
* Default → ya vienen con JS.
* Personalizadas → la hace el programador
Estructura de la *FUNCIÓN*:

![image](./img/funciones.png)

* La función tiene que realizar una acción (instrucciones)  con algo (parámetro).
* Los parámetros son datos.
* El nombre de la función tiene que ser corto y descriptivo.
* Tiene que hacer una sola cosa y hacerla bien.
* Para declarar la función se utiliza la palabra reservada function.
* Para poder “ejecutarla” tiene que estar declarada, se ejecuta o “llama” utilizando el nombre de esa función.

Ejemplo:
~~~
function restar (num1, num2){
            let resultado = (num1 - num2)
            alert (resultado)
        }

        restar (3, 2);
        restar (10, 5.5);
        restar (3, 5);
~~~

### Links a Ejercicios con los conceptos vistos 🏋️‍♀️:
* [Ejercitación Funciones](https://github.com/sandramuraca/ejercicios_funciones)

***

<a name="dom"></a>

## 🔴 DOM:

**Document Object Model** → representación estructural del documento HTML, que nos permite modificar su contenido // ARBOL BINARIO

![image](./img/dom.png)

🚩SELECTORES Y MÉTODOS🚩

Cada etiqueta representa un “nodo”.
Para poder modificar e interactuar con los elementos del HTML hay que usar “selectores” para poder identificar al elemento sobre el cual quiere efectuar el cambio o interacción.
¿Cómo puedo seleccionar un elemento?🤔

**Seleccionandolo por**:

* su id: `document.getElementById("#titulo");`
* su clase: `document.getElementsByClassName(".parrafo");`
* su etiqueta: `let listaDesodenada = document.getElementsByTagName("ul");`

Estos selectores corresponden a las siguientes etiquetas de un html:

![image](./img/dom2.png)

Con el id estamos seleccionando al `h1`, con la clase al `p>}` y con la etiqueta al `ul`
Una vez que los elementos están **“seleccionados”** utilizamos **MÉTODOS** para poder modificarlos.
* `miVariable.innerHTML` → puedo insertar otros elementos
* `miVariable.textContent`→ inserto texto
* `miVariable.style` → inserta atributo “style” madifica estilos en linea

### AGREGAR CLASES DESDE JS:
classList es una propiedad de JS que sirve para manipular clases a un elemento del DOM:
* `miVariable.classList.add` → agrega una clase
* `miVariable.classList.remove` → quita una clase
* `miVariable.classList.toggle` → busca una clase, si no la tiene la agrega, si la tiene la quita.

### SCOPE
Se considera el ámbito de alcance de una variables, si la variable se declara fuera de una función se puede reutilizar dentro de todas las funciones que se escriban luego.
Si se declara dentro de una función solo será válida dentro de esa función.
Ej:

![image](./img/scope.png)

En el ejemplo la variable `container` está declarada fuera de las funciones, por eso la puedo reutilizar en todas, caso contrario tendría que declararla dentro de cada función.

### EVENTOS
Podemos definirlos como: Interacciones que realizan los usuarios finales.💻
Es la manera de controlar las acciones del usuario y definir un comportamiento de la página cuando estos se produzcan. Cuando un usuario visita una web e interactúa con ella se producen eventos y con JS podemos controlar lo que queremos que ocurra cuando esos eventos se produzcan.
Evento = hacer click en un botón, escribir en un campo de texto, cambiar de página

* **Tipo de Evento**: es el nombre del evento que ocurre (por ejemplo click). 
Es un String con el nombre del tipo del evento --->`*“click” - “keypress”`
* **Target del evento**: es el objeto al cual le ocurre el evento o que está asociado a dicho evento (puede ser cualquier nodo del html).
* **Manejador de evento**: es una función (callback) que maneja o responde a un evento (Se lo conoce también como listener). función que se invoca cuando sucede el evento.

~~~
/*1. armar html
2. crear 3 botones diferentes
3. agregar un evento a cada uno
4. el evento tiene que disparar un alert*/
 
const primerBoton = document.querySelector("#boton1");
const segundoBoton = document.querySelector("#boton2");
const tercerBoton = document.querySelector("#boton3");
 
primerBoton.addEventListener("click", () => {
    alert ("usted a tocado el boton 1");
});
segundoBoton.addEventListener("click", () => {
    alert ("usted a tocado el boton 2");
});
tercerBoton.addEventListener("click", () => {
    alert ("usted a tocado el boton 3");
});
~~~
**Objeto del evento**: es un objeto asociado con un evento en particular que contiene detalles sobre el evento. 
Este objeto es pasado como parámetro de la función que maneja el evento. 
Las propiedades de este objeto cambian según el tipo de evento que sea. 
Ejemplo: puedo saber que tecla se presiona o posición del mouse dependiendo del tipo de evento que maneje.

**Lista de eventos que se pueden utilizar**:
* `onchange`
* `onclick / ondblclick / onmousedown / onmousedownonmouseover / onmouseout`
* `onkeydown / onkeypress / onkeyup`
* `onload`
* `onresize`
* `onscroll`
* `oninput`
* `onfocus / onblur`

📢 Para indicarle a un objeto que tiene que suceder algo cuando el usuario realice un evento ese objeto tiene que estar *“selccionado”* en el js con `querySelector(“#idDelObjeto”)`.
 
**stopPropagation** → evita la propagación del evento a objetos que que están dentro de un objeto al cual le indique que realice determinada acción ante un evento. Ejemplo si soy una indicación a un formulario, los elementos dentro de este, por propagación también realizarán esa indicación.
 
**preventDefault** → evita que el elemento seleccionado realice la acción que por defecto realiza, Ejemplo, recarga de la página en el botón `submit`.

~~~
event.stopPropagation();
// evita que se ejecute el evento del form ya que el boton esta dentro por default lo ejecutaria
event.preventDefault(); 
// esto evita que la accion que por defecto realiza el elemento se lleve a cabo
~~~

### Links a Ejercicios con los conceptos vistos 🏋️‍♀️:
* [Ejercitación DOM](https://github.com/sandramuraca/ejerciciosDOM)
* [Ejercitación Eventos](https://github.com/sandramuraca/ejercicios_eventos)

🔼 [VOLVER AL INDICE](#indice)