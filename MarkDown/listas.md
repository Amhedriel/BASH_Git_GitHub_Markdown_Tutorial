# **Listas**
Se pueden agregar tanto listas ordenadas como no ordenadas.

- [Listas ordenadas](#listas-ordenadas)
- [Listas no ordenadas](#listas-no-ordenadas)
- [Anidación de listas](#anidación-de-listas)
- [Elementos en listas](#elementos-en-listas)
- [Párrafos anidados](#párrafos-anidados)

- [Imágenes anidadas](#imágenes-anidadas)
- [Citas anidadas](#citas-anidadas)
- [Bloques de código anidados](#bloques-de-código-anidados)

[**&#11176;** *Anterior* &#11007;](/MarkDown/codigo.md "Código") 
[Siguiente **&#129042;**](/MarkDown/enlaces.md "Enlaces")

## Listas ordenadas
Se debe agregar un **número** seguido de un **punto**, un **espacio** y el **elemento de la lista**. No necesariamente debe estar ordenada pero debe comenzar por el `1`:

1. Primero elemento.
2. Segundo elemento.
3. Tercer elemento.

```
1. Primero elemento.
2. Segundo elemento.
3. Tercer elemento.
```
## Listas no ordenadas

Se puede utilizar un guion `-`, `+` o un asterisco `*`.

* Primer elemento
* Segundo elemento
* Tercer elemento

```
* Primer elemento
* Segundo elemento
* Tercer elemento
```
## Anidación de listas

Se pueden anidar listas ordenadas y/o desordenadas. Sin embargo deberán tener una **sangría** de al menos **cuatro espacios** o una **tabulación**:

1. Primero elemento.
    1. Primer elemento.
    2. Segundo elemento.

2. Segundo elemento.
    * Primer elemento
    * Segundo elemento

3. Tercer elemento.
    * Primer elemento
        * Segundo elemento

```
1. Primero elemento.
    1. Primer elemento.
    2. Segundo elemento.

2. Segundo elemento.
    * Primer elemento
    * Segundo elemento

3. Tercer elemento.
    * Primer elemento
        * Segundo elemento
```
## Elementos en listas

Es posible anidar otros elementos, como párrafos, citas, bloques de código o imágenes. Para ello debes agregar una línea en blanco y luego cuatro espacios o una tabulación antes del elemento.

## Párrafos anidados

Para incluir un **párrafo** en el interior de un elemento de una lista:

* Primer elemento
* Segundo elemento

    Un párrafo
    
* Tercer elemento
```
* Primer elemento
* Segundo elemento

    Un párrafo
    
* Tercer elemento
```

## Imágenes anidadas
También puedes incluir una imagen en un elemento de una lista. Para ello basta con que dejes una línea en blanco y añadas cuatro espacios o una tabulación antes del código Markdown de la imagen:
* Primer elemento
* Segundo elemento

    ![Imagen de unas nubes montañosas](/MarkDown/Img/LagoMonta%C3%B1oso.jpg)
    
* Tercer elemento
```
* Primer elemento
* Segundo elemento

    ![Imagen de unas nubes montañosas](/MarkDown/Img/LagoMonta%C3%B1oso.jpg)
    
* Tercer elemento

```

## Citas anidadas

Con que dejes un espacio en blanco y que luego dejes cuatro espacios en blanco o una tabulación antes de la cita:
* Primer elemento
* Segundo elemento

    > Cita
    
* Tercer elemento
```
* Primer elemento
* Segundo elemento

    > Cita
    
* Tercer elemento
```

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

En caso de no querer agregar tantos espacios al principio, tendrías que usar los bloques de código de la sintaxis extendida.

---

[**&#11176;** *Anterior* &#11007;](/MarkDown/codigo.md "Código") 
[Siguiente **&#129042;**](/MarkDown/enlaces.md "Enlaces")

[*Volver* **&ldca;**](/MarkDown/README.md "Regresar a página Principal") 
[*Subir* **&#11165;**](#listas "Ir al título")