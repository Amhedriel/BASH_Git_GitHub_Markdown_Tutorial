# Git rebase

Sabemos que en el flujo de trabajo de toda la vida podemos llegar a cometer un error bugfix y en esa rama empiezo a arreglar el bug, eventualmente cuando ya estoy listo para unir esta nueva rama a mi main el cual siguió haciendo sus cosas  `merge` y en ese `merge` pegamos lo que había en bugfix a la rama main y continuó con mi vida sin embargo la rama de bugfix pero qué pasa cuando el arreglo del bug realmente sí lo puedo hacer en otra rama pero quiero que se agregue en la historia, qué tal si lo que quiero no es hacer un `merge` si no hacer como que no pasó nada, lo que quiero en realidad es borrar esa rama que se llama bugfix pero pegar todos los cambios que hice y una vez la tengo borrada lo que hago es pegar esos cambios a la historia del máster y una vez pegados los cambios no se lo digo a nadie entonces todo está bien y seguimos con nuestra propia historia, y es como si no hubiera pasado nada, para poder hacer eso se debe hacer lo que se conoce como un `rebase` qué es básicamente agarrar una rama entera y pegarlas de regreso a la rama main, esto es una muy mala práctica enviándolo a repositorios remotos, esto se debería ser como mucho internamente, en general la historia en los repositorios remotos deberían mantenerse intacta, `rebase` es solo para repositorios locales porque reescribe la historia del repositorio, sería como un parche, funciona en ciertos casos usando tu criterio y preguntando a tus compañeros de trabajo si es que se puede solucionar con esto, sin embargo los errores  pasan así que aprendemos a solucionarlos.

Estamos en la rama main en la versión más reciente  de nuestros archivos vamos a abrir en este momento historia.txt para ver el seguimiento en esta historia.

En este archivo historia.txt tenemos toda la historia actual y vamos a agregar algo nuevo, Master 1, guardamos el cambio a nuestro archivo .txt:

		Git commit -am "Master 1"

Para mantener claro lo que está pasando porque un archivo puede cambiar, si vemos en este momento nuestro ``arbolito``:

		arbolito

vamos a descubrir que el origin/main qué está subido a internet se quedó un poquito atrás y que la versión más reciente la tiene nuestro main local, qué tiene la palabra "Mater 1".

Ahora hoy vamos a crear una nueva rama hice llamará:

		git branch experimento 

en esa rama vamos a crear una serie de cosas experimentales y para hacerlo debemos ingresar a dicha rama:

		git checkout experimento
		
ahora ya estamos en la rama experimento, en esta rama vamos a agregar a nuestro archivo historia.txt algo de texto llamado "Experimento 1". Lo guardamos y hacemos un:

		Git commit - am "exp 1"
		
Y si vuelvo a ejecutar mi comando `arbolito` veremos que origin/main está atrás tenemos unas ramas main que tiene la palabra Master 1, experimento tiene Experimento 1, esto simplemente como un experimento didáctico, vamos a crear otra línea que se va a llamar "Experimento 2", lo guardamos y continuamos con el comando:

		Git commit - am "exp 2"

En este momento si nosotros nos vamos de regreso haciendo un checkout a main, este es solamente tiene a Master 1, y el resto se fue, ahora si nosotros nos vamos de main a experimento entonces ahí vemos a Experimento 1 y  Experimento 2, eso significa que los branches hicieron por completo una desconexión ahora quiero pegar esos branches como si la rama experimental nunca hubiera existido y que estos experimentos se peguen a la rama main, para ello estando en la rama experimento voy a pegarme a la llama main: 

		git rebase main
		
Con esto lo que estamos haciendo es que: dentro de la rama experimento, al nivel de experimento le estoy diciendo que pegue mi historia a la historia del main. Al darle enter nos dice que mi rama está completamente actualizada, esto es porque main no ha cambiado, entonces hagamos algo mucho más interesante, volvamos a la rama main y en esta rama agreguémosle un "Master 2" al archivo .txt y guardamos los cambios.

		Git commit -am "Master 2"
		
Ahora volvamos a nuestra rama experimento, y si nos fijamos bien en nuestra llama experimento el cambio de "Master 2" no existe, porque las rama más adelantada actualmente tiene escrito "Master 2", entonces notamos que la rama que está un poquito más atrás es la rama experimento que tiene las otras líneas menos la línea "Master 2" y tenemos a la rama de internet que ni siquiera se ha enterado que todas estas cosas existen, entonces intentamos desde la rama experimento hacer un rebase a main.

		git rebase main  
		
Bueno bueno nos dice: primero, vamos a darle para atrás el `head` para ver los cambios que se hicieron y vamos a aplicar Exp 1, vamos a aplicar Exp 2 y vamos a hacer un auto `merge`, si vemos los resultados veremos que en la rama experimento nos trajeron todos los demás cambios, es como si hubiera vuelto a actualizar a la rama main, como si el check out original lo hubiera hecho desde el último y más reciente commit de main, esta es la magia de un `rebase`.

Si nosotros desplegamos nuestro ``arbolito``  la historia cambió, la historia ahora es que origin/main es la original, hubo "Master 1" también hubo "Master 2" y ahí fue donde se creo la rama experimento, la historia ya no es que la barra experimento arrancó un commit atrás, sino que la rama experimento arrancó un commit más adelante, por eso esto se considera una mala práctica porque cambia la historia de dónde arrancó el branch, pero es útil si nosotros estamos haciendo un cambio local, ahora yo podría ser lo mismo de toda la vida `merge` con la rama anterior y que quede todo lindo y listo.

	  git checkout main
	  git rebase experimento (aquí ya estamos dentro de main)
	
Y siempre el orden es así primero se le hace el rebase a la rama que voy a desaparecer de la historia y luego se hace rebase a la rama principal, si no se hace en este orden se entra en un conflicto súper extraño que solamente se arregla con git reset. 

Entonces una vez hicimos este ``git rebase experimento``, podemos ver lo que pasa: "reajustando el jet de tu trabajo a main", estando en la rama main mi archivo .txt tiene todos los archivos que se han cambiado tanto comoExperimento 1-2 y Master 1-2.

		arbolito

Nos dice que sí existió una rama experimento pero que toda la vida ha tenido el mismo contenido que ha tenido main, es como si no hubiera pasado nada nunca, no sabemos lo que está pasando acá pero hagamos un git pull para traer todos los cambios que se hayan realizado en la página, luego hagamos un git push y se envió todo. 

Prácticamente a nivel de historia no pasó nada la rama experimento no existe, es más yo puedo ir a:

		git branch -D experimento
		
Y esas ramas se borró, cuando tratamos de verlo en arbolito ya no es visible.

esto es un rebase, lo cual es hacer cambios silenciosos en otras ramas y volver a pegarlas en la historia de esa rama a una rama anterior haciéndole un rebase, debemos recordar que primero se le hace un rebase a donde van los cambios que queremos aplicar y luego un rebase a la rama final que será la que va a quedar, rebase primero la que cambia y luego rebase a la rama final.

En el mundo real lo que hace al revés es ajustar en donde estuvo el primer commit haciendo un merge desde el primero no desde el último, el problema es que no queda historia, no se sabe quién fue o quién hizo qué, y que en ocasiones si la rama main avanzó mucho puede tener una banda de conflictos que se deberá arreglarlo manual, hay que ser muy cuidadosos y experimentar mucho.

	
