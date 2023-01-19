# **Formato de texto**

A continuación vamos a ver como formatear el texto en negrita, en cursiva o aplicando ambos formatos a la vez.

- [Cursiva](#cursiva)
- [Negrita](#negrita)
- [Negrita cursiva](#negrita-cursiva)
- [Texto tachado](#texto-tachado)
- [Notas al pie](#notas-al-pie)


[**&#11176;** *Anterior* &#11007;](/MarkDown/README.md "Menú Inicial") 
[Siguiente **&#129042;**](/MarkDown/codigo.md "Código")


## Cursiva

Para agregar texto en cursiva debes usar **un solo asterisco \*** o **un solo guion bajo _** tanto al inicio como al final de lo oración que quieres marcar como cursiva. Si quieres poner en cursiva ciertas letras que estén en la mitad de una palabra, deberás agregar un asterisco ``*`` o un guion bajo ``_``, sin espacios, al comienzo y al final de las letras deseadas:

Esto es un *texto en cursiva*.
Esto es un texto parcialmente en cu*rsi*va.

Esto es un _texto en cursiva_.
Esto es un texto parcialmente en cu_rsi_va.
```
Esto es un *texto en cursiva*.
Esto es un texto parcialmente en cu*rsi*va.

Esto es un _texto en cursiva_.
Esto es un texto parcialmente en cu_rsi_va.
```
Sin embargo, has de saber que el uso de guiones bajos puede ser problemático cuando resaltas ciertos caracteres en medio de una palabra, ya que no existen un estándar claro sobre este tema, siendo incompatible con varias herramientas. Por ello, siempre será preferible usar un **asterisco**.

---

## Negrita

Para agregar texto resaltado en negrita tendrás que usar **dos asteriscos \*\*** o dos **guiones bajos \_\_** al principio y al final de lo oración que quieres resaltar. En caso de que quieras resaltar un texto que está en medio de una palabra, tendrás que agregar dos asteriscos ``**`` o dos guiones bajos ``__``, sin espacios, antes y después de las letras deseadas:

Esto es un **texto en negrita**.
Esto es un texto parcialmente en ne**gri**ta.

Esto es un __texto en negrita__.
Esto es un texto parcialmente en ne__gri__ta.
```
Esto es un **texto en negrita**.
Esto es un texto parcialmente en ne**gri**ta.

Esto es un __texto en negrita__.
Esto es un texto parcialmente en ne__gri__ta.

```
## Negrita cursiva

Para que en texto esté resaltado tanto en negrita como en cursiva al mismo tiempo debes agregar **tres asteriscos \*\*\*** o **tres guiones bajos ___** antes y después de una palabra o de una frase. En caso de que el texto que quieres que esté en negrita y en cursiva esté en mitad de una palabra, deberás agregar también tres asteriscos ``***`` o tres guiones bajos ``___`` sin espacios a ambos lados:

Esto es un ***texto en negrita y cursiva***.
Esto es un ___texto en negrita y cursiva___.
Esto es un texto parcialmente en ne***grita y cursi***va.
Esto es un texto parcialmente en ne___grita y cursi___va.

```
Esto es un ***texto en negrita y cursiva***.
Esto es un ___texto en negrita y cursiva___.
Esto es un texto parcialmente en ne***grita y cursi***va.
Esto es un texto parcialmente en ne___grita y cursi___va.
```
Además, también es posible combinar dos guiones bajos y **un asterisco __\*** de apertura junto con **un asterisco y dos guiones bajos \*__** de cierre. Del mismo modo, también puedes usar **dos asteriscos y un guion bajo \*\*_** como apertura junto con **un guion bajo y dos asteriscos de cierre _\*\***:

```
Esto es un __*texto en negrita y cursiva*__.
Esto es un **_texto en negrita y cursiva_**.
Esto es un texto parcialmente en ne__*grita y cursi*__va.
Esto es un texto parcialmente en ne**_grita y cursi_**va.
```

---
## Texto tachado

Para agregar un texto tachado en Markdown tendrás que usar dos guiones ondulados ~~ tanto antes como después del texto que quires tachar. Esto agregará una línea horizontal a través del texto. El texto tachado suele usarse para indicar que ciertas palabras o elementos son un error:

El siguiente texto ~~estará tachado~~ 

```
El siguiente texto ~~estará tachado~~ 
```

## Notas al pie

Muchas versiones de la sintaxis extendida de Markdown también permiten agregar **notas y referencias** sin la necesidad de sobrecargar la sintaxis del cuerpo del documento.

Cuando agregas una nota al pie, se agregará un **índice** que enlazará con la nota y que se mostrará al final del documento con independencia del lugar en donde la definas. Al hacer clic en el índice, saltarás hasta la nota referenciada, al final del documento.

Para agregar una nota tendrás que añadir **entre corchetes** un **acento circunflejo** seguido del nombre del **identificador** de la nota ``[^id]``. Los identificadores podrán contener números y letras, pero no espacios ni tabulaciones. Tendrás que usar el mismo identificador para relacionar el índice con la nota que se mostrará el pie de página.

Para definir el texto de la nota en sí mismo, tendrás que agregar, de nuevo **entre corchetes**, un **acento circunflejo** seguido del nombre del **identificador** de la nota ``[^id]``. Luego deberás agregar **dos puntos** y el texto de la nota en sí mismo.

El texto de la nota puede estar definido en una sola línea o en varias líneas.

---

[**&#11176;** *Anterior* &#11007;](/MarkDown/README.md "Menú Inicial") 
[Siguiente **&#129042;**](/MarkDown/codigo.md "Código")

[*Volver* **&ldca;**](/MarkDown/README.md "Regresar a página Principal") 
[*Subir* **&#11165;**](#formato-de-texto "Ir al título")