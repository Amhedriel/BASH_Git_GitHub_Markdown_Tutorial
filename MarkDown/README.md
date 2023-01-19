# **Markdown**

Revisaremos el como poder escribir MD de una manera mas estructurada.

- [Encabezados](#encabezados)
- [Párrafos y saltos de línea](#párrafos-y-saltos-de-línea)
- [Saltos de línea](#saltos-de-línea)
- [Líneas horizontales](#líneas-horizontales)
- [Citas anidadas](#citas-anidadas)
- [Citas compuestas](#citas-compuestas)
- [Anular Markdown](#anular-markdown)

[**&#11176;** *Anterior* &#11007;](/README.md "Menú Inicial") 
[Siguiente **&#129042;**](/MarkDown/formatoDeTexto.md "Formato de texto")
## **Encabezados**
Empecemos con los encabezados.

Si queremos algo como esto:

# Encabezado 1
## Encabezado 2
### Encabezado 3
#### Encabezado 4
##### Encabezado 5
###### Encabezado 6

Estos son los 6 encabezados que se pueden tener en MD, desde el título hasta el sexto encabezado

```MD
<!-- Una almohadilla generará encabezado tipo h1, con 2 tipo 2 con 3 tipo 3... hasta 6 -->

# Encabezado 1
## Encabezado 2
### Encabezado 3
#### Encabezado 4
##### Encabezado 5
###### Encabezado 6
```
Siguiendo la regla de HTML lo que debemos recordar es que el `#` sería el título y solo tener uno en cada documento.

---

## **Párrafos y saltos de línea**

Para generar un nuevo párrafo separa el texto con una línea en blanco (Pulsando dos veces intro).

Útil para realizar un salto de línea y empezar una frase en una línea siguiente dentro del mismo párrafo:

"Andando con sus patitas mojadas,

el gorrión

por la terraza de madera"

```md
"Andando con sus patitas mojadas,

el gorrión

por la terraza de madera"
```

---

## Saltos de línea

Lo más habitual es agregar párrafos en lugar de saltos de línea, de modo que el texto se adapte al contenedor en el que está. Sin embargo, en ocasiones es preferible romper el estilo de escritura por defecto y comenzar una nueva línea.

Para agregar un salto de línea con markdown basta con que dejes dos o más espacios en blanco con "ENTER":

Esta es una línea.  

Y esta es otra línea.

```
Esta es una línea.  

Y esta es otra línea.
```
La sintaxis equivalente al salto de línea en HTML es la etiqueta ``<br>``. A continuación puedes ver el código Markdown que crea una nueva línea, su equivalencia en HTML.

Afortunadamente existen alternativas a los dos espacios, ya que también podrás usar la etiqueta HTML ``<br>`` para agregar un salto de línea. Esta técnica también tiene una gran compatibilidad con la mayor parte de los editores Markdown:

Esta es una línea.<br>
Y esta es ota línea.

```
Esta es una línea.<br>
Y esta es ota línea.
```
---

## Líneas horizontales
Con Markdown también podrás agregar líneas horizontales, que resultan útiles para separar el contenido o las secciones de un documento.

Para crear una línea horizontal basta con que agregues tres o más **asteriscos** seguidos, tres o más **guiones** seguidos o tres o más **guiones bajos** seguidos:

***
---
___

```
***
---
___
```
Para que la línea horizontal se represente, los símbolos deben estar solos en la línea, sin otros caracteres ni espacios a la izquierda o a la derecha de los mismos.

```
```
```
---
## **Citas**

Para agregar citas se agrega el `>` justo delante del texto.

>Esto es una cita

```markdown
>Esto es una cita

>Continuación de la cita
```
Citas que ocupen varias líneas:

>Esto es una cita
>
>Continuación de la cita
```
>Esto es una cita
>
>Continuación de la cita
```
## Citas anidadas
Se pueden anidar agregando más de un signo `>`, lo que definirá la profundidad de la cita:

> Ayer comí higos
>
>> Y antes de ayer manzanas.
```
> Ayer comí higos
>
>> Y antes de ayer manzanas.
```
## Citas compuestas

Las citas también pueden contener otros elementos Markdown, **encabezados**, **listas**, **enlaces** o cualquier **formato de texto**:

>### Cita de ejemplo
>
> - Me he comprado la ***Xbox***.
> - Y arreglé el otro *ordenador*.
>
> Por *suerte* estoy bien ***casado***, más que `console.log("Feliz");`

```
>### Cita de ejemplo
>
> - Me he comprado la ***Xbox***.
> - Y arreglé el otro *ordenador*.
>
> Por *suerte* estoy bien ***casado***, más que `console.log("Feliz");`
```
---

## Anular Markdown

Markdown utiliza símbolos comunes para marcar el texto de una manera muy rápida, para poder utilizar estos símbolos deberás usar una barra invertida ``\``.

De esta forma anulas \*Markdown*.

    De esta forma anulas \*Markdown*.

---

[**&#11176;** *Anterior* &#11007;](/README.md "Menú Inicial") 
[Siguiente **&#129042;**](/MarkDown/formatoDeTexto.md "Formato de texto")

[*Volver* **&ldca;**](/MarkDown/README.md "Regresar a página Principal") 
[*Subir* **&#11165;**](#markdown "Ir al título")





