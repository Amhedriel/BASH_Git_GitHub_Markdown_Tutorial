# **Enlaces**

Para crear un enlace en Markdown debes situar **entre corchetes** el texto que quieres enlazar, también conocido como anchor. Seguidamente, debes usar **paréntesis** para definir la URL a la que debe enlazar en texto del enlace:

Me gusta el editor [Editor Markdown](https://bing.com>)

```
Me gusta el editor [Editor Markdown](https://bing.com>)
```
Es importante que no existan espacios entre el corchete de cierre ``]`` del texto del enlace y el paréntesis de apertura ``(`` del enlace.

- [Puntos ancla](#puntos-ancla)
- [Título del enlace](#título-del-enlace)
- [Formato del enlace](#formato-del-enlace)
- [Enlaces a Referencias](#enlaces-a-referencias)

- [Imágenes](#imágenes)
    - [Título de la imagen](#título-de-la-imagen)
    - [Imagen con enlace](#título-del-enlace)

[**&#11176;** *Anterior* &#11007;](/MarkDown/listas.md "Formato de texto") 
[Siguiente **&#129042;**](/MarkDown/tablas.md "Tablas")


Además, también puedes **crear enlaces rápidamente** a una URL usando únicamente un enlace, sin necesidad de definir un texto de enlace o anchor. Para ello deberás escribir un símbolo menor ``<`` seguido del enlace y un símbolo `>`
<https://bing.com>

```
<https://bing.com>
```
---

## Puntos ancla

Al igual que en HTML, también podrás enlazar a **puntos ancla** de la página actual o de otras páginas post poniendo el carácter sostenido ``#`` y el ``id`` de la sección a enlazar:

Enlace a la sección [Enlaces](#enlaces "Te envía al título")
```
Enlace a la sección [Enlaces](#enlaces "Te envía al título")
```

Del mismo modo, también podrás crear **enlaces** ``mailto`` a **direcciones de email** mediante la misma sintaxis que los enlaces a URLs:

<email@edulazaro.com>
```
<email@edulazaro.com>
```

No existe un estándar claro acerca de cómo se deben tratar los espacios en las URLs, por lo que, para garantizar la compatibilidad con el máximo número posible de aplicaciones Markdown, es recomendable codificar los espacios de los enlaces como %20:

```
[Enlace](https://dom.tld/una%20pagina)
```

---

## Título del enlace

También puedes agregar un **título al enlace**, que aparecerá cuando pases el cursor por encima del mismo. Para agregar un título a un enlace debes añadirlo entre **comillas dobles**, justo después del enlace:

Me gusta el editor [Editor Markdown](https:// "Mejor editor Markdown")
```
Me gusta el editor [Editor Markdown](https:// "Mejor editor Markdown")
```
El código HTML equivalente a la sintaxis Markdown anterior será este:
```
Me gusta el editor <a href="https://" title="Mejor editor Markdown">Editor Markdown</a>
```

## Formato del enlace

También puedes **agregar formato al texto** del enlace, pudiendo ponerlo en negrita, cursiva o negrita y cursiva. Para ello basta con que uses asteriscos ``*`` o guiones bajos ``_``, según corresponda, alrededor del enlace:

Enlace al **[Editor en negrita](https://bing.com)**.

Enlace al *[Editor en cursiva](https://bing.com)*.

Enlace al ***[Editor en negrita y cursiva](https://bing.com)***.
```
Enlace al **[Editor en negrita](https://bing.com)**.

Enlace al *[Editor en cursiva](https://bing.com)*.

Enlace al ***[Editor en negrita y cursiva](https://bing.com)***.
```
Además, también podrás marcar el enlace como si fuese código en línea agregando comillas invertidas al anchor del mismo:

Enlace al [`código`](https://bing.com).
```
Enlace al [`código`](https://bing.com).
```
## Enlaces a Referencias

Los enlaces a referencias son un tipo especial de enlaces de Markdown que permiten mejorar la legibilidad de las URLs. Los enlaces a referencias constan de dos partes; 
- Un enlace a la referencia y 
- La referencia en sí misma, localizada en cualquier parte del documento.

El enlace a la referencia consta a su vez de dos elementos que van **entre corchetes**, separados o no por un espacio. El primer elemento debe contener el **texto que se mostrará como enlace** o **anchor**, mientras que el segundo contendrá el **identificador a la referencia** que se debe enlazar:

Aprende a [programar con PHP][1]

Aprende a [programar con JavaScript][2]

Aprende a [programar con Python][2]
```
Aprende a [programar con PHP][1]
Aprende a [programar con JavaScript][2]
Aprende a [programar con Python][2]
```
Tal y como ves, los enlaces a referencias no contienen un enlace en sí mismo, ya que enlazarán al enlace que definamos para las referencias ``1`` o `2` en cualquier parte del documento.

Para **definir las referencias** debemos escribir primero el **identificador de la referencia** entre corchetes, seguido de dos puntos ``:`` y del **enlace** al que apunta la referencia, que opcionalmente podrá estar rodeado de los símbolos ``<`` y ``>``.

Opcionalmente, también puedes agregar el **título de la referencia** definido entre comillas simples, comillas dobles o paréntesis, que se corresponderá con el atributo ``title`` de HTML:

[1]: https://bing.com/php "Programa con PHP"

[2]: https://bing.com/javascript 'Programa con JavaScript'

[3]: <https://bing.com/python> (Programa con Python)

```
[1]: https://bing.com/php "Programa con PHP"
[2]: https://bing.com/javascript 'Programa con JavaScript'
[3]: <https://bing.com/python> (Programa con Python)
```
Las referencias podrán estar situadas en cualquier parte del documento. Lo más habitual es colocarlas al final de la sección actual o al pie del documento.

---

## **Imágenes**

Para agregar imágenes con Markdown debes agregar un **signo de exclamación** ``!`` seguido del **texto alternativo** o ``alt`` de la imagen entre corchetes y de la **URL de la imagen** entre paréntesis:
![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp)
```
![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp)
```
La representación HTML de la imagen será esta:

```
<img src="/MarkDown/Img/Monta%C3%B1asNevadas.webp" alt="Imagen de unas nubes">
```
## Título de la imagen
Es posible agregar un título a la imagen, que se corresponderá con el atributo HTML ``title``. Para ello, basta con que agregues el título del enlace **entre comillas** después del enlace, en el interior de los paréntesis:

![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp "Título del enlace")

```
![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp "Título del enlace")
```
## Imagen con enlace
Para agrear un enlace a una imagen, rodea todo el código Markdown de la imagen con ``corchetes`` y tras ellos, agrega el ``enlace entre paréntesis``:

[![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp)](/MarkDown/Img/Monta%C3%B1asNevadas.webp)

```
[![Imagen de unas nubes](/MarkDown/Img/Monta%C3%B1asNevadas.webp)](/MarkDown/Img/Monta%C3%B1asNevadas.webp)
```

---

[**&#11176;** *Anterior* &#11007;](/MarkDown/listas.md "Formato de texto") 
[Siguiente **&#129042;**](/MarkDown/tablas.md "Tablas")

[*Volver* **&ldca;**](/MarkDown/README.md "Regresar a página Principal") 
[*Subir* **&#11165;**](#enlaces "Ir al título")