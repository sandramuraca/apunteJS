# APUNTES JS 馃摎

Este apunte fue realizado con material obtenido en:
- Clases curso Desarrollo Front End - ADA 7ma.
- Notas tomadas del curso de Corseit de JS
- Notas del curso de Udemy de Fernando Herrera - Programaci贸n para principiantes
- Paginas consultadas en la web.

## Objetivo馃幆
Este apunte es un resumen de los conceptos principaes de JS, el A B C, para principiantes.
Para no perderse, ir ordenado y con ejemplos pr谩cticos de algunos ejercicios.
La idea es ir actualizandolo, e incorporar nuevos conceptos a medida que los vaya viendo.

<a name="indice"></a>

## INDICE 馃搼
* [INTRO:](#intro)
- Que es JS?
- Caracter铆sticas
- Formas de vincular HTML y JS

* [INSTRUCCIONES B脕SICAS:](#instrucciones)
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
    - `Operadores de comparaci贸n`
    - `Operadores L贸gicos`

* [SWITCH](#switch)

* [FUNCIONES](#funciones)

* [CLICLOS](#ciclos)
    * While
    * For

* [DOM](#dom)
    - Selectores
    - M茅todos
    - ClassList
    - Scope
    - Eventos
***
<a name="intro"></a>
# 驴Qu茅 es JavaScript?

JavaScript se cre贸 inicialmente para "dar vida a las p谩ginas web". 
Exist铆a un necesidad de generar *interacci贸n* con el usuario.
Los *programas en este idioma se denominan scripts* . Pueden escribirse directamente en el `HTML` de una p谩gina web y ejecutarse autom谩ticamente a medida que se carga la p谩gina.
Los scripts se proporcionan y ejecutan como texto sin formato. 
No necesitan preparaci贸n especial o compilaci贸n para ejecutarse.
Se lo considera un lenguaje de programaci贸n seguro. No proporciona acceso de bajo nivel a la memoria o la CPU, ya que se cre贸 inicialmente para navegadores que no lo requieren.

## 驴Qu茅 hace que JavaScript sea 煤nico?
Hay al menos tres cosas buenas sobre JavaScript:
- Integraci贸n completa con `HTML` / `CSS`.
- Las cosas sencillas se hacen de forma sencilla.
- Compatible con todos los navegadores principales y habilitado de forma predeterminada.

## Caracter铆sticas:
- D茅bilmente tipado
- Interpretado
- Din谩mico
- Secuencial: lee las instrucciones en orden de arriba hacia abajo.

## Formas de vincular HTML con JS:

1. Dentro de un archivo HTML una etiqueta <script> </script> indica un cambio de lenguaje, todo lo que est茅 dentro de ella estar谩 en JS, se coloca dentro del body y 馃毇 no se anidan 馃毇.
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
驴C贸mo?
Abriendo el archivo HTML con live server, haciendo click derecho `Inspeccionar`:
![image](./img/consola.png)

驴C贸mo escrib铆 ese c贸digo en JS?
~~~
<script>
   console.log("hola! soy un string y quiero que me veas por la consola");
</script>
~~~
La instrucci贸n 
~~~
console.log()
~~~
te permite ver lo que escribiste entre par茅ntesis (luego vemos qu茅 tipo de dato es).

Y si no lo quiero ver en la consola?馃
~~~
<script>
    alert("hola! soy un string y quiero que me veas por la consola");
</script>
~~~
La instrucci贸n
~~~
alert()
~~~
muestra un mensaje en el browser:

![image](./img/alert.png)

Otra instrucci贸n muy com煤n es 
~~~
prompt, 
~~~
QUE HACE 鉂?
Abre un cuadro de di谩logo con el usuario, donde le puedo hacer una pregunta, y su respuesta se convierte en un 鈥渄ato鈥?.
Pero el `prompt` no guarda el dato en ninguna parte, entonces... le har铆a una pregunta a un usuario y luego no podr铆a utilizar ese dato que me dio en su respuesta?馃

para eso vamos a utilizar las:
<a name="variables"></a>

### 馃敶 VARIABLES
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

Para entender esto 馃憜 tenemos que entender lo que es una
馃毄VARIABLE馃毄

Es un *espacio de memoria* (como una cajita 馃摝) donde se almacenan distintos tipos de datos.

Siempre tiene un *nombre que las identifica* que debe ser 煤nico.

**Se las puede nombrar de 3 formas**:
* `var` : en desuso
* `let`: puede cambiar su valor (ejemplo del nombre, si entra otro usuario, el nombre va a ser otro).
* `const`: no puede cambiar su valor.

Declarar e inicializar una variable es asignarle: 
* *Nombre* (declarar)
* *Valor* (enti茅ndase valor al dato que va a guardar) -> (inicializar)

Ejemplo:
~~~
<script>
    let nombre = "Sandra";
</script>
~~~

En este caso el *nombre de la variable* es 鈥渘ombre鈥? y el valor es 鈥淪andra鈥?. 
Como se que el valor es ese? 
Porque con el `signo =` se le asignan valor a las variables, se lo llama *OPERADOR DE ASIGNACI脫N*.

Cada vez que se termina de declarar una sentencia para cerrarla se debe colocar un punto y coma ( ; ) 鉂椻潡鉂?

Las variables se pueden declarar todas en una misma l铆nea separadas por comas:
~~~
<script>
    let nombre = "Sandra"; edad= 42; nacionalidad = "argentina";
</script>
~~~

En este ejemplo hay 3 variables: nombre, edad, nacionalidad.
Y los valores son: 鈥淪andra鈥?, 42, 鈥渁rgentina鈥?.

馃お por que 鈥淪andra鈥? y 鈥渁rgentina鈥? est谩n entre comillas y 42 no???? 馃憖

Porque todo lo que es *TEXTO 贸 STRING va entre comillas*, lo que es *N脷MERO* no  鉂椻潡鉂? y esto es as铆 porque esos datos son de distinto *TIPO*.

<a name="nombre_variable"></a>

### 馃敽 La importancia del nombre de la variables:
* Su nombre tiene que representar a los datos que almacena.
* Debe ser legibles por humanos.
* Evitar usar abreviaturas o letras sueltas.
* Tenga en cuenta las definiciones de su equipo de conceptos b谩sicos y atengase a ellas, ejemplo: Usuario = user.
* Caracteres disponibles: letras del alfabeto, menos la 帽; n煤meros, $, gui贸n bajo.
* No pueden iniciar con un n煤mero.
* JS tiene palabras reservadas que no se pueden utilizar para nombrar variables, ej: *if, for, function*.

### Formas de escribir una variable 鉁?:
* `camelCase`: primera letra en min y la primer letra de la segunda palabra en MAY.
* `snake_case`: palabras separadas por un guion bajo
* `PascalCase`: primer letra de la primer palabra en MAY y primer letra de la segunda palabra en MAY.

<a name="tipo_dato"></a>

## TIPOS DE DATOS 馃搳:

* Tipo de dato: contenido del valor.
* Tipo de datos primitivos: no son objetos, contienen informaci贸n y son inmutables:

* `STRINGS` 馃摑: cadena de texto
~~~
<script>
    let texto = "Un String es una cadena de texto";
    let nombre = "Sandra";
</script>
~~~

* `N脷MEROS` :
~~~
<script>
    let edad = 42;
    let edad = "42"
</script>
~~~

El n煤mero va 馃憖SIEMPRE SIN COMILLAS馃憖, en el segundo caso lo interpreta como texto.

Los n煤meros pueden ser:

* Positivos
* Negativos
* Decimales
* Con ellos se pueden realizar operaciones matem谩ticas 鉃曗灃鉃椻湒

* `BOOLEAN`: valor 鈥渢rue鈥? y 鈥渇alse鈥?.鉁斺潓
* `UNDEFINED`: indefinido, declarar una variable y no asignarle ning煤n valor.
~~~
<script>
    let nombre 
</script>
~~~
![image](./img/indefinido.png)

* `NULL`: nulo = valor especial que representa "nada", "vac铆o" o "valor desconocido. Sin valor en absoluto
* `NAN`: not a number, cuando queremos realizar una operaci贸n matem谩tica con un dato que no es un n煤mero.

### COMILLAS PARA DECLARAR UNA VARIABLE:
Se pueden usar:
* comillas dobles: 鈥? 鈥?  let nombre = 鈥淪andra鈥?;
* comillas simples: 鈥? 鈥?   let nombre = 鈥楽andra鈥?; (alt+39)
* backticks: let nombre = `Sandra`; (alt+96)
Las backticks se utilizan para una forma particular de *CONCATENAR*.

<a name="concat"></a>

### Que es CONCATENAR?:
Unir dos o m谩s cadenas de texto y datos.
Se puede concatenar con el signo + (opci贸n 1), o utilizando backticks (comillas inclinadas - alt+96) y ${} (opci贸n2)
Ejemplo:

1. 
~~~
let nombre = "Sandra";
let apellido = "Muraca";
let edad = 42;
 
alert ("hola soy" + nombre + "" + apellido + "y tengo" + edad + "" + "soy argentina y estudio programaci贸n");
~~~

2. 
~~~
let nombre = "Sandra";
let apellido = "Muraca";
let edad = 42;
 
alert (`hola soy ${nombre} ${apellido}y tengo ${edad} soy argentina y estudio programaci贸n`);
~~~

El resultado de ambas opciones es el mismo:

![image](./img/tipoComillas.png)

<a name="op_mat"></a>

### OPERADORES MATEM脕TICOS 鉃曗灃鉃?:
Para realizar operaciones matem谩ticas utilizamos los siguientes signos:

(+) SUMA
(-) RESTA
(/) DIVISI脫N
(*) MULTIPLICACI脫N
(%) RESTO

Existen otros operadores, como el de potenciaci贸n, decremento e incremento.

### Links a Ejercicios con los conceptos vistos 馃弸锔忊?嶁檧锔?:
* [Introducci贸n a JS](https://github.com/sandramuraca/introduccionJS)
* [Variables, Datos, Operadores](https://github.com/sandramuraca/VARIABLES_OPERADORES_DATOS)

馃敿 [VOLVER AL INDICE](#indice)
***
<a name="objetos"></a>
馃毄OBJETOS馃毄

En construcci贸n 馃敡馃敤馃洜鈿?

Es una representaci贸n abstracta de una cosa que existe en la vida real.
Esta cosa a su vez tiene propiedades, son las cosas que lo describen como tal. Ejemplo:

![image](./img/objeto.png)

Esta es una casa de color blanco, tipo chalet, tiene techo rojo, una ventana, un farol, una puerta y una chimenea, todo eso en JS se puede representar de la siguiente manera:
~~~
let casa = {
    color : `blanco`,
    tipo : `chalet`,
    puerta : 1,
    ventana : 1,
    farol: 1,
    chimenea: 1;
    techo : rojo
}
~~~

En este bloque de codigo se respeta la forma de escritura del string (con comillas) y n煤meros sin comillas.

Entonces los objetos son variables, que continen elementos que se denominan propiedades, que tambien son variables, pero que estan relacionadas con el objeto.
Para declarar una propiedad dentro de un objeto, cierro cada declaraci贸n con una coma (,) y el todas las propiedades de ese objeto se declaran entre llaves.

*Ejemplo de objeto y como utilizar sus propiedades*: en este ejemplo le pedimos datos a un usuario mediante `prompts` sus respuestas las almacenamos en `variables` y esas variables las utilizamos luego en las `propiedades` del `objeto`, los datos que queremos mostrar en el `alert` los llamamos desde una `funcion` :
~~~
let nombreUsuario = prompt ("Ingrese su nombre");
let edadUsuario = Number(prompt ("Ingrese su edad"));
let nacUsuario = prompt ("ingrese su nacionalidad"); 

function describirPersona (p) {
    console.log(`${p.nombre} tiene ${p.edad} y su nacionalidad es ${p.nacionalidad}`);
}

let persona = {
    nombre : nombreUsuario,
    edad : edadUsuario,
    nacionalidad : nacUsuario
}
describirPersona (persona);
~~~

### Links a Ejemplos:
* [Objetos y arrays con objetos](https://github.com/sandramuraca/ejercicios_objetos)

<a name="arrays"></a>
馃毄ARRAYS馃毄

Es una lista de elementos, que  tienen relaci贸n entre s铆. 
Se escriben entre corchetes [ ] 鈫? es un tipo de OBJETO.
Es una forma de agrupar elementos (de cualquier tipo).
Los elemtos de un array se separan por comas, y se escriben entre '', el arreglo tiene que tener un nombre y operador de asignacion para darle valor

Ejemplo:

Array FAMILY es el agrupamiento de los *objetos* que representan a cada integrante de la familia馃憞
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

Los arrays tienen **鈥溍璶dices鈥?** que es la posici贸n de cada elemento que agrupa, el indice siempre arranca en 0.

Ejemplo:
~~~
console.log (family); // aca en el console muestra los 3 elementos con su nro indice
~~~
![image](./img/array.png)

El elemento 0 de este array es 鈥淪andra鈥? y as铆 sucesivamente.

~~~
console.log (family[0]); // aca llamamos al elemento, con todos us componentes, indicado con el nro entre corchetes seg煤n el indice
~~~
![image](./img/array2.png)

Ese 铆ndice se utiliza para llamar a cualquiera de esos elementos desde la consola seg煤n su numeraci贸n.
En los arrays importa el orden de los elementos.
El potencial del arrays est谩 con los **M脡TODOS** que viene por default con JS 鈫? son funcionalidades previamente programadas, por ejemplo 鈥減ush鈥? 鈫?
nombreDeLaVariable.push()

~~~
 family.push({
            name: `gata`,
            surname: `flora`,
            age: 7
        }) 
        /// de esta manera se agregan elementos dinamicos al array
~~~

luego de haber agregado un elemeto m谩s al array, se hacemos console.log:

![image](./img/array3.png)

**Otros M茅todos:**


* Para para obtener el **dato de uno de los elementos del arreglo**, dentro del console.log llamo el nombre del arreglo y la posicion del elemento *(indice)* que quiero obtener entre corchetes:

~~~
 let colores = [ 'rojo', 'blanco', 'verde', 'amarillo' ];

 console.log( colores[2]) // verde
~~~

* Podemos tener **arreglos anidados** (un arreglo dentro de otro), para obtener un elemento de un array que esta dentro de otro array, se indica con las primeras llaves la posicion del array y en las segundas llaves, la posicion del elemento que quiero obtener:
~~~
let arregloCosas = [
    true,
    123,
    'Sandra',
    [ 'manzana', 'pera', 'limon', 'naranja']
];

console.log(arregloCosas[3][1]); // pera
~~~

**.length**
* Como obtener la cantidad de elemento del array:

~~~
let juegos = ['pacman', 'wonder boy', 'sugar rush', 'mario'];

console.log('largo del array juegos: ', juegos.length); // largo del array juegos: 4
~~~

**.lenght-1**
* Como objetener el primero y el 煤ltimo elemento del array:

~~~
let primero = juegos [0]; //para obetener el primero
let ultimo = juegos[juegos.length-1]; //para obetener el ultimo
console.log({ primero, ultimo}); // { primero: 'pacman', ultimo: 'mario'}  --> el console.log lo escribo entre corchetes para que el resultado me lo muestre como un objeto
~~~

**.unshifth**
* Para agregar un elemento al principio del array:

~~~
juegos.unshift('Ralph');
console.log(juegos);
~~~

**.push**
* Para agregar un elemento al final del array:
~~~
juegos.push( 'tetris' );
console.log (juegos); // ['pacman', 'wonder boy', 'sugar rush', 'mario', 'tetris']
~~~

**.pop**
* Para borrar el ultimo elemento de un array:
~~~
let juegoBorrado = juegos.pop()
console.log( {juegoBorrado, juegos} ); // { juegoBorrado: 'teris', juegos:['pacman', 'wonder boy', 'sugar rush', 'mario'] }
~~~

**.splice**
* Para borrar un/unos elementos determinados:
~~~
let pos = 1; //indico posicion a partir de la cual quiero borrar
let juegosEliminados = juegos.splice( pos, 2); //entre ()indico posicion y la cantidad de elementos a eliminar
console.log({juegosEliminados, juegos}); // {juegosEliminados: ['pacman', 'wonder boy'], juegos: ['sugar rush', 'mario']}
~~~

**.indexOf**
* Si quiero saber la posicion de un elemento:
~~~
let indexMario = juegos.indexOf('mario');// se debe escribir igual que en el array caseSensitive
console.log({indexMario}); // {indexMario:2}
~~~
Si el indexOf regresa -1 significa que no lo encontro, puede estar mal escrito


**ARRAYS MULTIDIMENSIONALES - MATRICES**
Cuando tendo un array dentro de otro.



<a name="control"></a>

### 馃毄ESTRUCTURAS DE CONTROL馃毄

* Podemos controlar el flujo del c贸digo y c贸mo queremos que se ejecute seg煤n se cumplan o no algunas condiciones.
* Se denominan *CONDICIONALES*:
    * `if`
    * `else if`
    * `else`

* **if**: (si entonces) espera una condici贸n **true** para ejecutar el c贸digo, si es **false** las instrucciones no se ejecutan y el programa sigue su flujo.

~~~
 let numero = 2;
        if (numero >= 2) {
            alert("El numero es mayor o igual a 2");
        }

~~~
![image](./img/if.png)

* **else** (si no) permite controlar que pasa si la condici贸n es falsa, no necesita ning煤n par谩metro, por que se ejecuta cuando el parametro declarado en if es  false.

~~~
   let numero = 1;
        if (numero >= 2) {
            alert("El numero es mayor o igual a 2");
        } else {
            alert ("el n煤mero no es mayor o igual a 2");
        }
~~~
![image](./img/else.png)

* **else if** (si entonces si) en el tercer camino, es una contra condici贸n.

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

Con los **condicionales** se utilizan en los par谩metros los **OPERADORES DE COMPARACI脫N**:

![image](./img/operadoreComparacion.png)

y tambi茅n los **OPERADORES L脫GICOS**:

![image](./img/operadoresLogicos.png)

(|| operador barra vertical= alt + 124)

### DFD DE UNA ESTRUCTURA DE CONTROL DE 2 CAMINOS:
![image](./img/dfd.png)

馃挕 LOS CONDICIONALES PERMITEN TOMAR DECISIONES RESPECTO DE QU脡 CAMINO VA A TOMAR MI CODIGO SI PASA UNA COSA U OTRA.

<a name="switch"></a>

馃毄SWITCH馃毄

Forma de anidamiento de m煤ltiples expresiones IF, ELSE IF, ELSE.
Su uso no siempre es necesario resulta 煤til para introducir eficiencia y claridad al c贸digo.
En su contenido se quiere evaluar. 
Ejemplo:
~~~
let diaDeLaSemana = Number(prompt ("Ingrese un n煤mero, le diremos a que dia de la semana corresponde"));
 
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

### Links a Ejercicios con los conceptos vistos 馃弸锔忊?嶁檧锔?:
* [Ejercitaci贸n Condicionales](https://github.com/sandramuraca/ejercicios_condicionales)

馃敿 [VOLVER AL INDICE](#indice)

<a name="funciones"></a>

### 馃敶 FUNCIONES:

Es un bloque de c贸digo **reutilizable** 馃攧.
Tipos:
* Default 鈫? ya vienen con JS.
* Personalizadas 鈫? la hace el programador
Estructura de la *FUNCI脫N*:

![image](./img/funciones.png)

* La funci贸n tiene que realizar una acci贸n (instrucciones)  con algo (par谩metro).
* Los par谩metros son datos.
* El nombre de la funci贸n tiene que ser corto y descriptivo.
* Tiene que hacer una sola cosa y hacerla bien.
* Para declarar la funci贸n se utiliza la palabra reservada function.
* Para poder 鈥渆jecutarla鈥? tiene que estar declarada, se ejecuta o 鈥渓lama鈥? utilizando el nombre de esa funci贸n.

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

### Links a Ejercicios con los conceptos vistos 馃弸锔忊?嶁檧锔?:
* [Ejercitaci贸n Funciones](https://github.com/sandramuraca/ejercicios_funciones)

***

<a name="ciclos"></a>

### 馃敶 CICLOS:

EN CONTRUCCI脫N 馃敡 鉀? 馃敤










<a name="dom"></a>

## 馃敶 DOM:

**Document Object Model** 鈫? representaci贸n estructural del documento HTML, que nos permite modificar su contenido // ARBOL BINARIO

![image](./img/dom.png)

馃毄SELECTORES Y M脡TODOS馃毄

Cada etiqueta representa un 鈥渘odo鈥?.
Para poder modificar e interactuar con los elementos del HTML hay que usar 鈥渟electores鈥? para poder identificar al elemento sobre el cual quiere efectuar el cambio o interacci贸n.
驴C贸mo puedo seleccionar un elemento?馃

**Seleccionandolo por**:

* su id: `document.getElementById("#titulo");`
* su clase: `document.getElementsByClassName(".parrafo");`
* su etiqueta: `let listaDesodenada = document.getElementsByTagName("ul");`

Estos selectores corresponden a las siguientes etiquetas de un html:

![image](./img/dom2.png)

Con el id estamos seleccionando al `h1`, con la clase al `p` y con la etiqueta al `ul`
Una vez que los elementos est谩n **鈥渟eleccionados鈥?** utilizamos **M脡TODOS** para poder modificarlos.
* `miVariable.innerHTML` 鈫? puedo insertar otros elementos
* `miVariable.textContent`鈫? inserto texto
* `miVariable.style` 鈫? inserta atributo 鈥渟tyle鈥? madifica estilos en linea

### AGREGAR CLASES DESDE JS:
classList es una propiedad de JS que sirve para manipular clases a un elemento del DOM:
* `miVariable.classList.add` 鈫? agrega una clase
* `miVariable.classList.remove` 鈫? quita una clase
* `miVariable.classList.toggle` 鈫? busca una clase, si no la tiene la agrega, si la tiene la quita.

### SCOPE
Se considera el 谩mbito de alcance de una variables, si la variable se declara fuera de una funci贸n se puede reutilizar dentro de todas las funciones que se escriban luego.
Si se declara dentro de una funci贸n solo ser谩 v谩lida dentro de esa funci贸n.
Ej:

![image](./img/scope.png)

En el ejemplo la variable `container` est谩 declarada fuera de las funciones, por eso la puedo reutilizar en todas, caso contrario tendr铆a que declararla dentro de cada funci贸n.

### EVENTOS
Podemos definirlos como: Interacciones que realizan los usuarios finales.馃捇
Es la manera de controlar las acciones del usuario y definir un comportamiento de la p谩gina cuando estos se produzcan. Cuando un usuario visita una web e interact煤a con ella se producen eventos y con JS podemos controlar lo que queremos que ocurra cuando esos eventos se produzcan.
Evento = hacer click en un bot贸n, escribir en un campo de texto, cambiar de p谩gina

* **Tipo de Evento**: es el nombre del evento que ocurre (por ejemplo click). 
Es un String con el nombre del tipo del evento --->`*鈥渃lick鈥? - 鈥渒eypress鈥漙
* **Target del evento**: es el objeto al cual le ocurre el evento o que est谩 asociado a dicho evento (puede ser cualquier nodo del html).
* **Manejador de evento**: es una funci贸n (callback) que maneja o responde a un evento (Se lo conoce tambi茅n como listener). funci贸n que se invoca cuando sucede el evento.

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
Este objeto es pasado como par谩metro de la funci贸n que maneja el evento. 
Las propiedades de este objeto cambian seg煤n el tipo de evento que sea. 
Ejemplo: puedo saber que tecla se presiona o posici贸n del mouse dependiendo del tipo de evento que maneje.

**Lista de eventos que se pueden utilizar**:
* `onchange`
* `onclick / ondblclick / onmousedown / onmousedownonmouseover / onmouseout`
* `onkeydown / onkeypress / onkeyup`
* `onload`
* `onresize`
* `onscroll`
* `oninput`
* `onfocus / onblur`

馃摙 Para indicarle a un objeto que tiene que suceder algo cuando el usuario realice un evento ese objeto tiene que estar *鈥渟elccionado鈥?* en el js con `querySelector(鈥?#idDelObjeto鈥?)`.
 
**stopPropagation** 鈫? evita la propagaci贸n del evento a objetos que que est谩n dentro de un objeto al cual le indique que realice determinada acci贸n ante un evento. Ejemplo si soy una indicaci贸n a un formulario, los elementos dentro de este, por propagaci贸n tambi茅n realizar谩n esa indicaci贸n.
 
**preventDefault** 鈫? evita que el elemento seleccionado realice la acci贸n que por defecto realiza, Ejemplo, recarga de la p谩gina en el bot贸n `submit`.

~~~
event.stopPropagation();
// evita que se ejecute el evento del form ya que el boton esta dentro por default lo ejecutaria
event.preventDefault(); 
// esto evita que la accion que por defecto realiza el elemento se lleve a cabo
~~~

### Links a Ejercicios con los conceptos vistos 馃弸锔忊?嶁檧锔?:
* [Ejercitaci贸n DOM](https://github.com/sandramuraca/ejerciciosDOM)
* [Ejercitaci贸n Eventos](https://github.com/sandramuraca/ejercicios_eventos)

馃敿 [VOLVER AL INDICE](#indice)