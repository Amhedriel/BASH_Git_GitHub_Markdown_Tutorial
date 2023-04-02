# GitHub pages

Git hub tiene un servicio de hosting gratis el cual se denomina github pages, tú puedes tener un repositorio donde el contenido de tu repositorio se vaya a GitHub y este online como en cualquier otro servicio de hosting.

Ahora vamos a crear los rápidamente y lo que se tiene que hacer es abrir pages.github.com, es un sitio en el que te dice que es para tus proyectos donde lo único que tienes que hacer es tener un repositorio costeado y ahí te lo explica. Para poder utilizarlo debes ir a tugithub.com crear un nuevo repositorio con tu nombre de usuario y que tengan la extención de .github.com

A modo de ejemplo digamos que tenemos un usuario con el nombre de freddier y el nombre del repositorio colocamos el mismo freddier, en la descripción colocamos: ejemplo de un github page. Es muy importante que esto sea público, y lo creamos.

si tienes la llave s eh configurada sólo tienes que copiar la dirección y crearlo, en la máquina local se clonar el repositorio nuevo:

		git clone git@github.com:freddier/freddier.git
		
Y con eso ya estás y ahora hacemos el comando `ls -al` vamos a ver todos los archivos que ahora tenemos sin embargo encontramos un nuevo archivo que se llama freddier, qué es la nueva carpeta que justamente clonamos así que cambiamos de directorio para entrar a él `cd freddier` y vemos que sólo tenemos un archivo .git, ahora la recomendación es una vez dentro de nuestro repositorio crear un archivo llamado index.html:

		vim index.html
		
Y creamos el típico índex de prueba. Una vez esté listo lo guardamos y hacemos nuestro primer commit iniciamos con un:

		git add index.html
		
		git commit -m "Mi primer diseño de página en GitHub"
		
		git pull origin main

Pero no tengo ninguna referencia a main por lo tanto utilizo:

		Git remote -v
		
vemos que tengo fetch y push sin embargo como nunca hice ni siquiera el primer ``push`` debemos hacerlo ahora :

		git push origin main
		
Lo envía y revisamos nuestro repositorio ahí debería estar nuestro index.html con ejemplo en github page, sin embargo nos faltan algunas cosas más lo primero que hacemos es ir al nombre del usuario en este ejemplo sería freddier.github.io esta es la url especial, recordemos que mientras yo haya colocado un repositorio con el mismo nombre del usuario de github, entonces ahora tocaría dejarlo configurado para que este repo sea el que cargue github pages.

Ahora bien estando ya a la página principal de github nos vamos a settings nos vamos a la opción de github pages que agarre el main branch así debió quedar grabado, podemos tener cualquier otra rama y pedir que esa rama específica sea la que se muestre.

Ahora revisemos que en los shoppings generales nosotros tenemos el nombre del repositorio qué sería freddier y tenemos abajo 2 opciones para elegir la primera sería por si queremos que nuestro repositorio sea una especie de template para otros y la segunda nos pide la firma de los colaboradores a nuestro repositorio cuando los commits o cambios son subidos desde la web de github. ahora también debemos notar que en la barra de la izquierda nos da la opción de pages y ahí podemos ver toda la configuración que hicimos anteriormente.

Después de haber hecho esto el sitio ya está conectado con mi main branch y podemos ver la url de nuestro sitio web, un problema sería ver que nuestra dirección es algo larga en cambio en otras páginas les carga desde la raíz, para hacer esto y que no sea en lugar de /freddier sería hacer esto.

Ahora para que la página te funcione realmente como una página principal se debe colocar el nombre del repositorio freddier.github.io donde freddier es el nombre del creador de este repositorio, y una vez he nombrado entonces ya está, vamos a settings, github pages, ingresar al url que tenemos y escribir en el navegador la dirección de nuestro índice: /index.html.