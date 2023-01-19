# **Código**

En markdown también puedes definir bloques de código, tanto en línea como en forma de bloque.

- [Código en línea](#código-en-línea)

- [Bloques de código](#bloques-de-código)
  - [Bloques estándar](#bloques-estándar)
  - [Resaltado de sintaxis](#resaltado-de-sintaxis)
  - [Bloques de código anidados](#bloques-de-código-anidados)
  
- [Código HTML](#código-html)

[**&#11176;** *Anterior* &#11007;](/MarkDown/formatoDeTexto.md "Formato de texto") 
[Siguiente **&#129042;**](/MarkDown/listas.md "Enlaces")

## Código en línea

Para agregar código en línea en Markdown tendrás que usar comillas invertidas alrededor del texto que quieres que tengo formato de código:

Cambia de directorio con el comando `cd`

```
Cambia de directorio con el comando `cd`
```
En caso de que el texto que quieres denotar como código ya incluya comillas invertidas, debes usar comillas invertidas dobles para escapar las comillas internas y que el código se muestre sin errores de formato:

``let str = `texto de la cadena`;``
```
``let str = `texto de la cadena`;``
```
Si el código comienza o finaliza con una comillas invertida, tendrás que dejar un espacio entre la comillas perteneciente al código y las que uses para abrir o cerrar el código en línea:

``let str = `texto de la cadena` ``
```
``let str = `texto de la cadena` ``
```

## **Bloques de código**

Si el código que quieres agregar consta de más de una línea, puedes agregar un bloque de código. para ello basta con que uses al menos **cuatro espacios** o una tabulación al inicio de la línea:

    let num = 5;
    num++;
```js
    let num = 5;
    num++;
```
La versión equivalente en HTML del bloque anterior será la siguiente:

```html
<pre>
    <code>
        let num = 5;
        num++;
    </code>
</pre>
```
La sintaxis extendida de Markdown también posibilita la creación de bloques des código sin la necesidad de que tengan los cuatro espacios de sangría o la tabulación. Para ello, dependiendo del procesador de Markdown que utilices, tendrás que iniciar y cerrar el bloque de código con **tres tildes invertidas** ``(```)``, o **3 virgulillas** `~~~`.

---
## Bloques estándar

Son aceptados por la mayor parte de los procesadores de texto y herramientas Markdown. Su funcionalidad se limita a crear un bloque de código sin formato ni resaltado de sintaxis.

```
const value = 3;
let result = value * 4;
```
~~~
```
const value = 3;
let result = value * 4;
```
~~~

---
## Resaltado de sintaxis

Muchos procesadores Markdown soportan los bloques de código con resaltado de sintaxis para una gran cantidad de lenguajes de programación. Esto coloreará y agregará formato al código según el lenguaje de programación con el que se corresponda.

Para ello tendremos que **indicar el lenguaje** de programación **tras las tres comillas de apertura** del bloque de código.

A continuación agregamos un bloque de código JavaScript:

```javascript
const mongoose = require('moongose');

moongose.set('useFindAndModify', false);
moongose.connect('mongodb://localhost/node-notes-db', {
    useCreateIndex: true,
    useNewUrlParser: true
})
    .then(db => console.log('DB is connected'))
    .catch(err => console.error(err));
```
~~~
```javascript
const mongoose = require('moongose');

moongose.set('useFindAndModify', false);
moongose.connect('mongodb://localhost/node-notes-db', {
    useCreateIndex: true,
    useNewUrlParser: true
})
    .then(db => console.log('DB is connected'))
    .catch(err => console.error(err));
```
~~~
También podemos abreviar el lenguaje:
```js
const mongoose = require('moongose');

moongose.set('useFindAndModify', false);
moongose.connect('mongodb://localhost/node-notes-db', {
    useCreateIndex: true,
    useNewUrlParser: true
})
    .then(db => console.log('DB is connected'))
    .catch(err => console.error(err));
```
~~~
```js
const mongoose = require('moongose');

moongose.set('useFindAndModify', false);
moongose.connect('mongodb://localhost/node-notes-db', {
    useCreateIndex: true,
    useNewUrlParser: true
})
    .then(db => console.log('DB is connected'))
    .catch(err => console.error(err));
```
~~~

---
## Bloques de código anidados

Para agregar un bloque de código a un elemento de una lista debes dejar un espacio en blanco y luego debes agregar 8 espacios o dos tabulaciones antes del mismo:

* Primer elemento
* Segundo elemento

        let num = 5;  
        num++;
    
* Tercer elemento

```
* Primer elemento
* Segundo elemento

        let num = 5;  
        num++;
    
* Tercer elemento
```

---
## Código HTML

Podrás añadir directamente código HTML a los documentos Markdown, ya que la mayor parte de los editores y procesadores Markdown soportan código HTML.

Sin embargo, siempre es recomendable consultar la referencia o el manual de las aplicaciones que utilices para comprobar si soportan o no código HTML. En algunos casos se soportarán ciertas etiquetas, pero no todas ellas.

Resulta muy habitual usar HTML para cambiar el color del texto o modificar los parámetros de una imagen.

En este ejemplo resaltamos un texto usando tanto Markdown como HTML:

Puedes resaltar un texto con **markdown** o con <strong>HTML</strong>
```
Puedes resaltar un texto con **markdown** o con <strong>HTML</strong>
```
La versión HTML del código anterior será en todo caso la siguiente:

```
Puedes resaltar un texto con <strong>markdown<strong> o con <strong>HTML</strong>
```
También puedes usar código HTML para crear tablas o muchos otros elementos siempre que estén soportados por la aplicación que utilices.

Cuando agregues código HTML organizado en varias líneas, debes dejar siempre una línea en blanco tanto antes como después del bloque de código HTML. Además, no debes dejar espacios ni sangrías al comienzo de las etiquetas, ya que podría dar lugar a errores de representación.

Además, no es posible usar la sintaxis Markdown en el interior de las etiquetas HTML:

**<em>markdown<em>**

```
**<em>markdown<em>**
```
---

[**&#11176;** *Anterior* &#11007;](/MarkDown/formatoDeTexto.md "Formato de texto") 
[Siguiente **&#129042;**](/MarkDown/listas.md "Listas")

[*Volver* **&ldca;**](/MarkDown/README.md "Regresar a página Principal") 
[*Subir* **&#11165;**](#código "Ir al título")