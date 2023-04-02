# Dividiendo las ramas

En este ejemplo, yo (dueño del repositorio) me encargaré de la rama *header* y mi colaboradora (Anita) se encargará del *footer*, en mi *header* quiero agregar un logo, debo guardar esta imagen **dragon.png** en mi carpeta de *media* destinado para las imágenes, el problema es que una imagen es un archivo binario, no es un archivo de texto plano, entonces, por el tamaño, debemos pensarlo en agregarlo al repositorio o no, las mejores prácticas dictan: los archivos binarios no se deben agregar a repositorios, deberían estar aparte, deberían ser ignorados, sin embargo a falta de recursos en este repositorio los estamos agregando.

## Ramas

Lo primero que se debe hacer es un ``checkout`` para cambiar la rama, debido a que ya no estaremos trabajando directamente con el `main`, ya que ahí solo se envía lo que yo estoy seguro que está listo para producción, esto es una buena práctica en el trabajo, entonces hacemos cambio de rama:

    git checkout header

Estando en esta rama revisaremos por curiosidad la estructura de nuestro `arbolito`.
Después de revisar lo que necesitaba, haré un:

    git add imagenes/dragon.png

No envía ningún resultado en pantalla, pero revisamos lo sucedido con `git status` y veremos que está agregado y listo para hacer el ``commit``.

    git commit -m "logo del header"

Nos dirigimos a internet y lo revisamos en el repositorio nos daremos cuenta que todavía no existe, porque todavía no se lo envió a internet.

Recordemos que primero haremos un: 

    git pull origin header

El ``head`` es decir el apuntador de la última version del commit que está en internet es el mismo que tengo yo, entonces realicemos el `push`.

    git push origin header

Si nos vamos a GitHub, en la rama de `header`, nos informa que hace algún tiempo sucedió un evento, nos mostrará un ***compare & pull request***, pero aún no haremos nada con esto, pero si revisamos bien nos dirigimos al `branch header` y salio imágenes, y podemos revisarlo. Pero cuál es el problema?, esta imagen es pesada, son 232 kb, eso significa que siempre que yo haga cambios, voy a traerme este cambio también y entre más binarios le agregue al archivo más pesado va a ser el repositorio.

Debemos tomar en cuenta que los binarios en GitHub son raros y en ocasiones no actualiza su versión en caché, por lo tanto no deberíamos depender de Github, si como ejemplo, yo copio el link donde está la imagen y lo copio en el navegador directamente nos mostraría la imagen que actualizamos, pero a diferencia del texto que es siempre preciso, los sitios como GitHub agregan un caché intermedio que a veces puede tardar en actualizarse, si queremos forzar la actualización en Windows, es con CTRL + SHITF + R o con CTRL + F5.

Ahora queremos hacer algunos cambios al proyecto de blog.

por lo cual en la rama de `header` cambiamos el html y los estilos CSS entonces debemos subir los cambios para que no se pierdan:

    git commit -am "color de fondo, logo nuevo y mejor color de header"

Muy bien con eso estamos seguros que se guardaron los cambios realizados, porque si yo hago:

    git checkout main

Lo perdería todo, de hecho si vemos las carpetas veríamos que la carpeta imágenes se borró, porque en el ``main`` no tenemos ningún cambio realizado. Pero si cambiamos con `git checkout header` podremos ver la carpeta y todos los cambios realizados con esta rama.

---

## Revisión de ramas

Pero, digamos que ahora quiero ver que hizo "Anita", a quien dijimos que no tiene que hacer cambios directos a `main` sino que debería trabajar en `footer` pero yo no lo conozco y como no tengo zsh sino tengo la terminal normal, no sé donde estoy, se que estoy en hyperblog, y si le doy `git status` aparentemente estoy en el ``branch main``, entonces o que se debe hacer es traer de internet la rama `footer`, para eso hago el comando:

    git pull origin footer

El siguiente paso es:

    git checkout footer

Con esto hice cambié a la rama `footer`

    git status

Y parece que todo está bien

    git branch

Y me muestra que ahora tengo 2 ramas y estoy en la rama `footer` ahora mismo, con:

    ls -al

Veo todos los cambios.

Entonces, lo primero que Anita hará es crear toda la estructura del `footer` en HTML.

Una vez terminado el trabajo, se debe realizar el versionado de archivos:

    git status -s

Para ver los cambios de manera resumida, utilizamos:

    git commit -am "Footer terminado"

regresamos a nuestra carpeta principal, de ahí a `hyperblog/` y actualizamos los archivos con:

    git pull origin footer
    git push origin footer

Anita al revisar el GitHub puede encontrar los cambios que hizo.

## Uniendo ramas

El super usuario o admin revisa los cambios realizados en GitHub. vamos al bash y cambiamos de rama a `main`

    git checkout main

Y revisar como está la rama principal.

Ahora revisaremos las otras ramas.

    git checkout header
    git pull origin header
    git checkout footer
    git pull origin footer

Como soy el encargado del proyecto debo ser el que fusione las ramas de trabajo. Al revisar las ramas y ver que los trabajos están bien se debe ir a la rama principal de la que quiero hacer el `merge`:

Primero voy a hacer `merge` a mi cambio de `header`.

Nos vamos a la rama `main` con:

    git checkout main

Asi que desde la rama `main` voy a fusionar la rama del `header`:

    git merge header

Si no hay conflictos nos muestra el ``vim`` si queremos o por información podemos cambiar o agregar información en el título del commit.

    Merge branch 'header' para agregar el nuevo logo, color de fondo y header final

Con: ESC SHIFT Z Z
Guardamos todos los cambios y salimos.

Revisemos ahora que estamos en la rama `main` cómo esta presente la página del proyecto, deberíamos ver que los cambios realizados en la rama `header` deberían ser ahora visibles con `main`, Ahora enviemos esto a GitHub:

    git pull origin main
    git push origin main

Eso significa que si ahora vamos a GitHub/hyperblog en la rama `main` podemos ver los cambios realizados.

Como jefe ahora debo hacer un `merge` con el trabajo de Anita.










