# APUNTES JS

Este apunte fue realizado con material obtenido en:
- Clases curso Desarrollo Front End - ADA 7ma.
- Notas tomadas del curso de Corseit de JS
- Notas del curso de Udemy de Fernando Herrera - Programación para principiantes
- Paginas consultadas en la web.

# Por que hice este apunte?
Cursando la certificación de FrontEnd, me encontré numerosas veces con un sentimiento de frustración y enojo, por no entender algunas cosas o no encontrar material simple.
Bueno, como no encontre un apunte con esas características... lo hice.

Este archivo inició en un word en Drive, y como ca creciendo y mutando, lo pase a este .md para poder tenerlo siempre actualizado y que este disponible para aquel que puediera necesitarlo.

### Objetivo:
Este apunte es una especie de "machete" de los conceptos principaes de JS, el A B C, para principiantes.
Para no perderse, ir ordenado y con ejemplos prácticos de algunos ejercicios.

***

# ¿Qué es JavaScript?

JavaScript se creó inicialmente para "dar vida a las páginas web". 
Existía un necesidad de generar *interacción* con el usuario.
Los *programas en este idioma se denominan scripts* . Pueden escribirse directamente en el HTML de una página web y ejecutarse automáticamente a medida que se carga la página.
Los scripts se proporcionan y ejecutan como texto sin formato. 
No necesitan preparación especial o compilación para ejecutarse.
Se lo considera un lenguaje de programación seguro. No proporciona acceso de bajo nivel a la memoria o la CPU, ya que se creó inicialmente para navegadores que no lo requieren.

## ¿Qué hace que JavaScript sea único?
Hay al menos tres cosas buenas sobre JavaScript:
- Integración completa con HTML / CSS.
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

# Todo lo que se escriba en JS puede leerse en la “consola”.
¿Cómo?
Abriendo el archivo HTML con live server, haciendo click derecho “Inspeccionar”:
![image](./consola.png)


