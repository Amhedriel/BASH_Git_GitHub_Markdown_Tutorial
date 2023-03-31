# Subir archivos a GitHub

## Agregar origen remoto

Lo que haremos es subir nuestros archivos al repositor de GitHub

1. `git remote add origin https://...`

Pareciera que no paso nada para si escirbimos:

    git remote

veremos que esxiste algo llamado ``origin``, y si escribimos:

    git remote -v

Nos mostrará los:

    origin https://...git (fetch)
    origin https://...git (push)

una vez hecho esto ya lo tenenmos todo listo, veremos que al hacer:

    ls -al
Veremos entre los archivos el .git, etc, y a continuación escribimos:

    git push origin master

Con esto decimos que: Git envíale al origen (https://...git) la rama master o main dependiendo del nombre que colocamos.

Para poder hacer el cambio de la rama `master` a la rama `main` debemos:

    git branch -m main

De esta manera indicamos que estamos trabajando actualmente con la rama `main`. Ahora para llevar esto que tenemos ahora localmente a nuestro repositorio de GitHub debemos colocar:

    git push origin main

Si tenemos un error de datos por conflicto de `push` lo recomendable es leer las instrucciones y si el único conflicto que se nos presenta es el de *updates* rechazados porque el remoto con el que se está trabajando no está localmente entonces debemos traer los cambios realizados en otro push para después poder subit los cambios actualmente realizados, o sea hacer un `fetch` pero hoy en día generalmente hacemos un `pull origin master`

    git pull origin main

Nos puede mostrar algunos *Warnings* eh indicarnos bastante información, sin embargo en el error:

    fatal: refusing to merge unrelated histories

Que significa: Me rehuso a fusionar historias no relacionadas, una historia es un grupo de `commits`, podemos forzarlo de estam manera:

    git pull origin main --allows-unrelated-histories

Lo cuak nos permite fusionar lo que tenemos allá con la rama que tenemos en local, suele ser un problema aislado y es porque GitHub tiene un problema con la estructura que crea estos archivos.

Ahora nos está permitiendo hacer el `merge` con la rama main, le indicamos que sí lo queremos hacer en el editor que nos muestra.

Hecho esto revisemos la información que nos mnuestra y veremos que trajo algunos archivos que no teníamos localmente, generalmente es el README que creamos al principio en la página de GitHub, este tipo de erroes suelen aparecer por hacer cambios directamente en los repositorios alojados y no desde nuestro editor local, sin embargo también puede deberse al no haber actualizado correctamente el repositorio local antes de empezar a trabajar y olvidar que se habrían hecho cambios anteriormente desde otro lado, el cual suele ser mi caso.
  
Ahora volvemos a intentar un:

    git status

si no nos muestra mingún conflicto con lo que tenemos hecho continuamos con:

    git push origin main

Revisamos que no hayan conflictos y que el ``main`` local se envió al ``main`` de GitHub.

Como último, relizamos un:

    git status

Para ver si todo anda de maravilla, y continuamos trabajando de ser así.



