# Forks

Es una característica única de github en la que se crea una copia exacta del estado actual de un repositorio directamente en github este repositorio podrá servir como otro origen y se podrá clonar (como cualquier otro repositorio), hoy en pocas palabras, lo podremos utilizar como un git cualquiera.

Un ``fork`` es una bifurcación del repositorio completo, tiene una historia en común, pero de repente se bifurca y pueden variar los cambios ya que ambos proyectos podrán ser modificados en paralelo y para estar al día un colaborador tendrá que estar actualizando su fork con una información del original. 

Al hacer un ``fork`` de un proyecto en github, te conviertes en dueño del repositorio ``fork``, puedes trabajar en este con todos los permisos pero es un repositorio completamente diferente que el original, teniendo alguna historia en común. 

Los ``forks`` son importantes porque es la manera en la que funciona el *open source*, ya que, una persona puede no ser colaborador de un proyecto, pero puede contribuir al mismo haciendo mejor software que pueda ser utilizado por cualquiera.

Al hacer un ``fork``, github sabe que se hizo el ``fork`` del proyecto, por lo que se le permite al colaborador hacer pull request desde su repositorio propio. 

## Trabajando con más de un repositorio remoto

Cuando trabajamos en un proyecto que existe en diferentes repositorios remotos (hoy normalmente a causa de un ``fork``) es muy probable que desees poder trabajar con ambos repositorios, para esto puedes crear un *remoto adicional* desde consola:

    git remote add <nombre_del_remoto> <url_del_remoto>
    git remote upstream https://github.com/...

 Al crear un *remoto adicional* podremos, hacer ``pull`` desde el nuevo ``origen`` (en caso de tener permisos podemos hacer ``fetch`` y ``push``) 

    git pull <remoto> <rama>

    git pull upstream main

Este `pull` nos traerá los *cambios del remoto*, por lo que se estará al día con el proyecto, el flujo de trabajo cambia, en adelante se estará  trabajando haciendo **pull request** desde el app stream y **push al origin**, para pasar a hacer **pull request**.

    git pull upstream main

    git push origin main

## Proyecto open source

A continuación veremos un ejemplo de cómo funciona un proyecto open source.

Vamos a convertir el proyecto de ejemplo en un proyecto open source donde el dueño es Freddier y Anita simplemente es una persona que le gusta el proyecto y quiere aportar, para ello tendríamos que ir a los settings de nuestro proyecto, ir a collaboratiors y eliminar a esta colaboradora, ahora que no es un colaborador ya no puede hacer ``merge`` directo lo que sí puede hacer es clonar el proyecto pero no puede hacer ningún tipo de ``push`` porque no tendrá permisos. 

Ahora digamos que Anita quiere colaborar con el proyecto pero de modo externo el primer paso para poder colaborar con el proyecto es darle en el botón de watch porque de ese modo me llegarán notificaciones en el momento en el que salgan cosas nuevas, lo segundo que se puede hacer es colocar una estrellita porque es un indicador de anclar el proyecto, por lo tanto también llegarán avisos si hay cambios en el proyecto, luego hacemos un ``fork`` lo cual es hacer una copia del estado actual del proyecto y clonarlo para poder tener una copia mía, esto sólo se puede hacer con proyectos públicos y es una característica única de Github.

Entonces le vamos a hacer clic a fork y en este mismo instante estoy copiando el proyecto a un nuevo repositorio, incluso podremos ver el historial de commits.

Y en esta tabla de github podemos ver incluso una pestaña de release en el que tiene un tag versión 0.1, que lo puedo descargar ya sea en zip o tar.gz.

## Copiarlo a disco en local

Para lograr hacer eso tengo que traerme el proyecto, en github tengo que ir al mi repositorio al cual yo le hice ``fork``, y desde ahí recién hacer un ``clone``.

Una vez copiado el https vamos a la consola allí en la carpeta donde nosotros queremos tener este proyecto, clonamos el proyecto: 

    git clone https://github.com/mipaginadegithub/elproyecoalquelehicefork.git 

Como este es un repositorio público no nos pide credenciales simplemente lo copia y listo, ahora si nosotros entramos en la carpeta del repositorio clonado y hacemos el comando `ls -al` podemos ver los archivos qué clonamos.

A partir de acá ya podemos hacer un `git status` hoy comprobar que estamos en la rama ``main``.

Si hubiera un cambio puntual el cual yo quisiera arreglar o proponer lo edito directamente con mi editor de consola `vi blogpost.html`.

Y bueno solamente para dejar claro que yo hice alguna modificación acá buscaré un archivo `vi historia.txt` y podríamos agregar algo de información nuestra, ESC, SHIFT, Z, Z para salir del editor guardando los cambios podemos hacer un `git status` para ver todos los cambios que se hicieron, también hacemos un `git diff` para estar seguros de lo que hicimos es correcto y continuamos con un:

	git commit -am "tildes con identidades y un mensaje de contribución"
	
Con eso nos sale un mensaje en el que nos indica que estamos en la rama main y que nuestra rama está más adelante de la rama de la rama main del origen qué es el que está en internet por 1 commit, es decir que mi historia es un poco más fuerte, entonces lo que debemos hacer es:

	git push

Y con esto podemos ver que funcionó como solo tenemos un lugar entre el origen y el main no necesitamos agregar origin/main en este caso, pasa que generalmente se hace `git push remote origin` porque es una buena práctica, ya he hecho vayamos a mi repositorio en github y revisemos los cambios, si nos metemos a nuestro historial vemos los cambios que hicimos y toda la información que queramos, sin embargo este es nuestro proyecto si nosotros queremos hacer un `merge` entre un proyecto y otro, como github sabe que este proyecto es un ``fork`` que sería una bifurcación desde el proyecto original entonces github nos ayudará a hacer esto de manera muy fácil solamente debemos cliquear en el botón new pull request e inmediatamente nos abrirá una interfaz donde nos dice: "escoge las 2 ramas para saber qué cambió y empezar un pull request, si lo necesitas también puedes comparar los diferentes forks ". Si elegimos los diferentes forks nos vamos a la diferencia entre el main que yo tengo como base y el la mente está del otro lado, comparando a través de los forks.

Github es una muy buena herramienta que nos permite hacer cosas como estas, ahora que ya tenemos claro cuál es el pull request de qué forma lo podemos modificar, iremos a create pull request que es como hacer un commit intermedio el cual sería como "esto es lo que irá en el commit si me permites hacer el merge" entonces ahí nos muestra el mensaje que anotamos en el cómic y podemos dejar un comentario, podemos colocar algo como "me encanta este proyecto y quería aportar con una mejora en las tildes" y podemos poner un emoji si queremos.

No debemos olvidar que también podemos editar el pull request si los que lo mantienen o los dueños del proyecto original quieren cambiarlo, con eso ya podemos crear el *pull request* o *create draft pull request* que sería algo así como esperar a hacer algo que quiero y luego enviarlo.

Podemos ir al repositorio del proyecto principal y mirar a los datos que hayamos hecho o hayamos cambiado hoy sin embargo lo único que podemos hacer es cerrar el pull request y rendirnos en caso de que no nos hayan aceptado o podemos seguir comentando y esperar. 

Ahora como dueño del proyecto principal podemos ver una notificación y nos indica que alguien hizo pull request en este caso de ejemplo tenemos a Anita, y vemos que quiere hacer un `merge` o fusión desde su rama main hacia mi rama main.

En este caso no tengo mucho de que preocuparme solamente ver los cambios que hizo, vemos que no tiene ningún conflicto y que no va a romper nada, porque si habría algún conflicto tendríamos que devolverle y pedir que arregle estos conflictos, podemos ver los cambios.

Si revisando todo nos parece que está bien entonces podemos escribir un mensaje en este caso con un "OK" bastaría y hacemos clic en la opción de Approve, que sería el cambio fue aprobado, ahora hacemos *merge pull request*, confirmamos el **Merge**. Y con esto fusionamos las ramas `main` y al hacer esto también nos trajimos la historia de Anita, y bueno esto es que si yo hago cambios ella va a tener que traérselos en su propio fork.

