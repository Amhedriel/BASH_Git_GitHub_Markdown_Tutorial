# Historia de nuestro proyecto

Nosotros sabemos que en las aplicaciones hay varias versiones son como una hasta aca llegó el proyecto y esto vamos a enviar, para poder realizar esto nosotros debemos ver el historial de nuestro proyecto

## Git **`log`**

Nosotros ya sabemos que usando `git log` podemos ver el historial De todos los commits que hicimos hasta ahora.

Ahora para que nos muestre literalmente todo lo que hemos hecho históricamente:

    git log --all

Resulta que también tenemos emoción especial que es:

    git log --all --graph

Y al momento en el que agregas puedes ver que nos muestran unas rayitas para ver cómo se han ido fusionando las dos ramas, así nos puede mostrar esto de una manera visual. Sin embargo aún se le pueden agregar más cosas. 

    git log --all --graph --decorate --oneline

De esta manera nos mostraría todo mucho mas comprimido para que sea más fácil revisaron su historial. Así obtenemos el allí exacto de cuando ocurrió cada commit.

Sin embargo debemos reconocer que el comando es muy largo y probablemente es muy difícil recordar este comando, así que nosotros le pondremos un nombre muy corto podríamos ponerle arbolito.

Este es un truco del mundo de Linux que se llaman ``aliases``, lo que hace es que al colocar entre comillas el comando que quiere reducir y enfrente que escribes alias con el nombre del alias que le quieres colocar en este caso arbolito y le seguimos de un igual a modo de variable.

        alias arbolito="git log --all --graph --decorate --oneline"

Una vez hecho esto nosotros podemos escribir ``arbolito`` y nos mostrará todo el historial de la misma manera que con el comando completo.

```BASH
$ arbolito
* 7de4cd0 (HEAD -> main, origin/main) push y log
* 15b0a39 Agregando trucos
* 7676c86 Agredando interactividad en codigo.md
* dd92169 Actualización 1.0
```
## `tags`

Debemos tener en mente que esto es distinto para cada persona empieza crear sus propios aliases, sabemos Carlos allanar de aliases estarán guardados en nuestro entorno local desconocía se podrá trabajar, cuando estamos hablando de aliases estamos hablando de ``tags``. Ahora que tenemos está claro revisando el ejemplo que tenemos con arbolito digamos que nosotros queremos crear un tal que nos gustaría que en cierto lugar donde reemplazo una versión por otra versión pero antes del *block post*, nosotros sigamos que tenemos a esta:

    * 7676c86 Agredando interactividad en codigo.md

Esta sería la versión más reciente de la historia sería como si fuera la versión 0.1 de mi proyecto entonces crearemos un tag ahí.

La forma en que se crearon tal es así primero copiamos el **hash** de tu commit ``7676c86 Agredando interactividad en codigo.md``. Entonces escribe ``git tag -a``, esto significa que voy a agregar un ``tag``, luego la colocación nombre que quieras pero la convención es colocar `v0.1` que sería que esta es la versión 0.1 de mi proyecto. A continuación le agregamos un espacio y al igual que en commit enviará un mensaje con `-m` entre comillas y el mensaje es `"Resultado agregando interactividad al proyecto básico"`. El indicamos en donde vamos a insertar el tag, el tajo va estar en este hash `7676c86`

    git tag -a v0.1 -m "Resultado agregando interactividad al proyecto básico" 7676c86

Después de presionar enter pareciera que no pasó nada sin embargo ahora tengo que ver cuáles son los tags que ya tengo.

    git tag

Cuando tú escribes `git tag` sin nada más te va a mostrar la lista de todos los tags.

Ahora bien como quita es especial y es un proyecto de código abierto donde muchas personas han ido a metiendo mano, la forma de saber a que hash o a que commit está conectado un ``tag`` sería con: 

    git show-ref --tags

Y al presionar entre marrón mostrar que tenemos un tag llamado v0.1 y que está asignado a este hash que lo mostrara completo, hecho en ese commit.

Si nosotros utilizamos un: `git status`. Nos aparecerá que nosotros no tenemos ningún cambio que enviar porque los `tag` no son cambios, sin embargo sí hay algo que enviar porque la idea es que los tags lo puedan ver alguien, los tags son útiles en GitHub, en el sitio web porque es la forma que usuarios en el código abierto pueden ver que versión ocurrio, Esos tags en últiles en un proyecto, donde quieres dejar un registro de aquí fue donde quede, simplemente es más como referencia interna, entonces lo interesante es enviar la internet y es eso lo que vamos a hacer.

Ahora recordemos que nosotros siempre debemos hacer un:

    git pull origin main

Antes de hacer cualquier cambio, para ver que todo lo que está en internet te lo traigas para acá.

Ahora vamos a enviar el `tag` a GitHub:

    git push origin --tags

Conocer, no estamos diciendo que vamos a empujar a origen que se repositorio de GitHub los `tags` los que estamos trabajando.

## Borrar `tag`

Qué pasa si queremos borrar un tag entonces tendríamos que,


    git tag -a dormido-m "Que cansansio"

Entonces nos traemos todo lo que hay que traerse de internet coma haciendo un ``pull`` y luego con el comando.

    git push origin --tags

Ahora vamos a nuestro repositorio en github vemos en el apartado de branch main y al revisarlo en ``tag`` veremos que tenemos nuestro ``tag dormido``, 

Sin embargo al revisarlo nos damos cuenta que nos confundimos y no queremos más este ``tag dormido`` como entonces cómo deshacerse del ``tag dormido``. Lo mismo puedo hacerlo desde la interfaz bonita de git sin embargo tendríamos que saber borrarlo desde el bash, la forma de `borrar` un tag es sencillo primero escribimos: 

    git tag

y nos mostrará todos los ``tags`` que tenemos hola, entonces ahí veríamos nuestro ``tag dormido`` y para eliminarlo tenemos que hacer el comando:

    Git tag -d dormido

Y con esto nos aparece el mensaje de `tag` eliminado.

Si usamos el comando de guide status no nos dirá nada porque no cambiamos ningún archivo, si nosotros hacemos pull para traerlo y luego hacemos el push de los tags nosotros podemos ver que todo está bien, sin embargo si vamos a nuestro repositorio de github y revisamos en los branch los tags veremos que aún sigue el tag dormido. 

La razón por la que no se borra automáticamente este tag de github es porque se pueden usar como *relyses* qué es la forma en la que tu tagueas o categorizas que algo está listo, entonces aunque lo borres internamente queda el registro de que sigue ahí nuestro tag, pero entonces lo que tenemos que hacerlo es borrarlo de una manera muy especial: 

    git push origin :refs/tags/dormido

Esta es una sintaxis interna que borra esa referencia al lugar de origen conectado con nuestra referencia de cuando borramos el tag al darle enter esperamos un rato y vemos un mensaje en el que nos dice que aparentemente está borrado vamos a la página de github revisamos dónde están los tags y veremos que realmente ya no está el tag que borramos, de esta manera es como se crean y se borran tags.

## ``history``

Un modo de ver el historial más completo de todos los comandos que hicimos con Git.


