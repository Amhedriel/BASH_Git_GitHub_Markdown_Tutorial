# Migrar a Servidores

Hasta el momento sabemos que la rama main es la que normalmente se manda al servidor de  producción, depende del flujo de trabajo de cada persona, por qué por ejemplo hay grupos de trabajo qué es lo que hacen es que le ponen ``taks`` a la rama que se envía a producción  y ese es el el ``tag`` que se envía a producción, cuál es la forma de enviar a producción es fantástica porque es muy similar a lo que estuvimos trabajando todo este tiempo.

Imaginando que nosotros tenemos un blog y que tenemos entre nuestros archivos un blogpost.html.

A lo que vamos a hacer es traerlo a una url qué se llama freddier.com, este es un servidor que yo compré hace un tiempo, ese recomendaría hacer un curso de administración de servidores, Dev Ops, para entender bien cómo hacer este servidor, digamos que ya sabes montar ese servidor en linux así que vamos a entrar a la carpeta donde se guardan los archivos del servidor:

		cd /var/www/freddier.com/html/
		ls -al
		
Me diría que hay un total de digamos 16 pero yo me concentraría en el index.html, como quiero revisar el contenido que tiene hago un:

		cat undex.html
		
Y me mostraría el contenido:

		<strong>Solo un test</strong> del sistema.

Podemos revisarlo en el navegador colocando esa dirección, en el mismo navegador podemos escribir freddier.com/test.html, y nos mostraría lo que tenemos en ese documento html: "Es una prueba", y si nosotros vemos en el servidor veremos que efectivamente hay un archivo que dice test.html y si lo abrimos con el anterior comando:

		cat test.html
		
		Es una prueba

Para este ejemplo es un servidor nginx que se configuró en un proveedor de cloud, lo que vamos a hacer es traer unos para acá nuestro repositorio qué es hyperblog, lo que hacemos es copiar el https desde el repositorio en la carpeta del servidor colocamos el comando:

		Git clone https://githubcom/freddier/hyperblog.git

    ls -al

Ahí podemos ver los archivos, y si gay nos vamos al server que contratamos y entramos a su url www.freddier.com/hyperblog/ Nos va a salir un error porque al navegador no sabe a qué le está apuntando, pero nosotros sabemos que hay una carpeta con el nombre de hyperblog, pero debemos abrirlo: www.freddier.com/hyperblog/blogspot.html

Con esto ya podríamos ver el documento html que está alojado actualmente en esa dirección en nuestro servidor.

Y de este modo podríamos hacer cambios directamente desde github, haciendo un cómic directamente a la rama main aunque podríamos crear una nueva rama para este propósito `merge` hoy como debería ser pero al ser este es un ejemplo práctico ya hicimos el commit lo enviamos nos vamos al repositorio vemos los cambios que ya están hechos, si vamos al URL de nuestro sitio veremos que aún no hay ningún cambio realizado, por qué aún tenemos que ser un ``pull`` entonces nos dirigimos a la consola y buscamos ingresamos a la carpeta hyperblog

		Cd hyperblog
		
Si ingresamos a la carpeta podemos ver el contenido `ls -la` e incluso el .git, hacemos un `git status` porque bueno ya tenemos instalado Twitter nos indicará en la rama en la que estamos y que estamos al día con la rama de 'origin/main', hoy no necesitamos tener permisos porque como es un repositorio público lo único que tengo que hacer es traerme la última versión por lo tanto escribimos:

		git pull origin main 
		
con esto nos hace cambio en el blogpost  y ahora vamos de nuevo a nuestro sitio en internet y a los de cargar veremos los cambios que realizamos, esta es la base más sencilla para hacer un `Deploy`.

debemos tener cuidado porque esta no es una buena práctica para ser diploides esta sería una muestra muy pequeña y el grano, porque alguien podría tener acceso al archivo git y entonces nuestra base de datos de cambios a través de esto, entonces lo que debemos hacer es proteger nuestro .git si nosotros usamos Apache hay una forma, si usamos nginxhay otra forma, esto no forma parte de un curso de git esto ya sería un curso de DevOps, y un curso de administración de servidores.

 También hay formas más avanzadas de hacer esto como hay una página que se llama travis-ci.org qué es como un github que el lo que hace es conectar directamente tus ramas de github con tus servidores, tú le colocas permisos de tu servidor, permisos de github y cuando tú le haces push a una rama "deploy" este automáticamente detecta eso y lo va a mandar, si por ejemplo tienes código que tiene que ser construido como un javascript que tiene que tener procesos con CSS o stylus automáticamente puede disparar esos procesos. Travis cuesta dinero es pero si lo estás usando para hacer proyectos open source no te cobran, aunque también tienes jenkins.io que es otro sistema que te permite hacer esto pero este se instala, jenkins es increíblemente poderoso, pero también es increíblemente complejo, se explican en los cursos de integración continua. Integración continua y desarrollo continuo es como se le llama esto en el mundo de DevOps.

## Resumen

**Deploy** es el proceso que permite enviar al servidor uno o varios archivos. Este servidor puede ser de prueba, desarrollo o producción.

En el siguiente ejemplo veremos cómo se realiza el deployment de un documento en un servidor web básico.

## Pasos para hacer deployment en un servidor web:

- entrar a la carpeta de los archivos del servidor.

- Copiar link en *clone*, elegir entre HTTPS o SSH del repositorio a contribuir.

En la carpeta deseada se clona el repositorio:

    git clone url

    Deploy:

* Realizar cambios y *commit* en GitHub.

* Traer al Repositorio local las actualizaciones para el servidor en la carpeta de los archivos del servidor.

    git pull ramaRemota main

> *Nota: siempre se debe proteger el archivo.git. Dependiendo del software para el servidor web, existen diferentes maneras. La conexión entre GitHub y el servidor se puede realizar mediante: Travis (pago) o Jenkis (Open Source).

