# Ramas o branchs

En github siempre vas a estar trabajando con ramas, la rama principal dónde está la última versión, pero qué pasa con las otras ramas de desarrollo; normalmente una versión estable de tu software y luego de a pocos vas creando cambios los cual es no están seguros si vas a agregar o no a la rama principal, o también puede que hayan múltiples programadores trabajando en partes distintas, digamos que estamos haciendo un blog y lo vamos a dividir el desarrollo de la cabecera en una rama, el desarrollo del pie de página en otra rama.

ya usamos las ramas cabecera pero para efectos prácticos a partir de ahora la rama de cabecera la vamos a llamar header, de tal manera que la cabecera que manejemos local quede como una historia y el header es donde nosotros manejamos el cambio de la parte de arriba y el footer será al cambio de nuestro pie de página, simularemos ser programadores distintos.

	1. Vamos a agregar la historia de las ramas a github y luego vamos a crear estas 2 ramas nuevas.

como un recordatorio importante a las ramas:

	  git checkout cabecera
	
Recordemos que checkout y el nombre de la rama es lo que te permite cambiar de rama, entonces ``git checkout cabecera`` me devuelve a cabecera y me cambia todos los archivos en mi disco duro, y sí coloco ``git checkout main`` me devuelve a main.

	git branch

Me muestra todas las ramas que en este momento existen, en este ejemplo serían ``cabecera`` y ``main``, recordemos que tenemos creado algo llamado ``arbolito`` el cual nos muestra la historia de estas ramas, también nos muestra que el tag dormido que creamos antes nos lo borró. 

Hay otros comandos importantes que aún no vimos pero son necesarios para manejar las ramas, uno de ellos es:

		git show branch

Que nos muestra cuáles son las ramas que existen y seguir su historia también tenemos:

		git show branch --all
		
que nos va a mostrar todo de una manera similar pero con un poco más de datos.

Analicemos el output de este comando:

```BASH
Git show branch --all

![cabecera] modifique la cabecera y el color del texto
  *  [main] Una versión del hyperblog
    ! [origin/main] una versión del hyperblog
---
*+ [main] Una versión del hyperblog
*+ [main~2^2] Initial commit
...

```
La primera línea me muestra que hay una rama llamada cabecera que fue la primera vez que se creó, también tenemos una llamada main, hay otra rama llamada origin/main, qué es la que está en remoto estas son las 3:00 ramas que de momento existen.

y también nos muestra más o menos históricamente cuál ha sido la historia más reciente de cada una de esas ramas.

## **`gitk`** 

Tenemos este comando muy especial que al instalar git nos viene por defecto, y lo que hace es abrirnos en un software esa historia de una manera gráfica en donde tenemos toda la historia y así podemos ver qué cambios se han hecho.

Sin embargo algo que debemos saber es que todos los desarrolladores profesionales utilizan la consola, este comando con el software visual es una ayuda pero sin la consola nos vas a poder trabajar rápido, utiliza esto si necesitas tener una versión visual históricamente para darte una idea de cómo está estructurado tu proyecto, siendo la cabecera, el main, etc. Debemos tener siempre en mente que los profesionales trabajan con consola.

---

Muy bien para la versión más sencilla simplemente:

	Git branch

me has entender que hay 2 ramas main y cabecera, pero no hemos enviado cabecera, y enviarlo es tan fácil como colocar:

	Git pull origin main

Ahora vamos a movernos en nuestra barra de cabecera:

	Git checkout cabecera

Hacemos:

	Git push origin cabecera

Es decir vamos a empujarle a `origin ` que es el nombre de nuestra rama en internet la rama cabecera. 

Podemos ir a ver a github todos los cambios que hicimos, vamos entonces a nuestro repositor y en lo que es branch vemos las ramas que tenemos podamos seleccionar cualquiera y ver el historial de qué cambios se hicieron.

Tú puedes tener ramas que nunca envíes al repositorio de trabajo en internet como también puedes tener ramas que siempre estás enviando, no importa lo importante es que se aprenda a manejar bien este proceso de ramas. 

Ahora que tenemos la rama de cabecera creada vamos a crear un par de ramas más; con lo que crea haremos otras ramas de trabajo header y footer y olvidémonos por ahora de cabecera que va a crear simplemente como una rama de referencia. 


Volvamos a nuestra rama principal.
	git checkout main
Y estamos nuevamente en main.

Ahora vamos a crear las otras ramas:
	
	git branch header
	
	git branch footer
	
Con el comando de git branch podemos ver que ya tenemos esas ramas creadas 

Vamos a enviar esto a internet para que si alguien copia de internet de estos datos los va a tener muy claro, entonces vamos a darle:

	Git push origin header

Y esto va a enviar mi rama header.

	Git push origin footer

Esto va a enviar mi llama ``footer``  tbn ahora lo interesante será ver cómo es el flujo de trabajo, imaginemos que hay otro programador completamente distinto que se va a cargar a hacer el footer yo me encargaré de ser el header, qué pasa cuando ese programador quiere fusionar su trabajo the footer con el trabajo de header y cuando los 2 estamos listos enviarlo master eso es lo que va a ser muy interesante. 

Y eso es básicamente un flujo de trabajo en github.
