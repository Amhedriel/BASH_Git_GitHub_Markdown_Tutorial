# Pull request

Nosotros ya vimos cómo hacer un ``merge`` al main directamente de la rama ``header`` qué es la que tenía todos nuestros cambios en el ``header`` del blog y también el de la rama ``footer`` el cual hizo Anita revisamos cómo estaban las ramas y las unimos al ``main``, esa es la manera de trabajar pero en un entorno profesional generalmente se bloquea la ``main``, la idea es que nadie pueda hacer merge a los main simplemente porque sí y que en el proceso antes haya un *code review* la forma en que generalmente funciona en el mundo real de la programación es la siguiente:

Hoy imagina que tienes una rama ``main`` que es la principal y debemos entender que esa rama es la que eventualmente se subirá al servidor, específicamente al nuestro servidor de producción, que es donde generalmente se suele llamar al lugar en donde está nuestra versión final, hoy lo que sería nuestro sitio web, dónde está la versión final de compilación de una aplicación móvil antes de enviarlo a la app store y a la Play Store, pero a veces tenemos que hacer pruebas en un entorno que se parezca al de producción, debemos hacer pruebas en un entorno que sea tan similar como sea posible al entorno de producción sin que afecte a los usuarios.

Podemos imaginar un sitio que se llame **"hyperblog.com"** que es el sitio que estamos trabajando en el ejemplo, pero tenemos un dominio que se llama **"hyperblogtest.com"** para hacer pruebas lo que sería un subdominio. Cuando estamos desarrollando aplicaciones móviles nosotros tenemos apps de pruebas y la app a la que se envía como versión final directamente a la app store o Play Store coma entonces ese tipo de servidores normalmente se llaman servidores de desarrollo o servidores de **"staging"**, se pone un poco confuso porque ``staging`` también es el área donde nosotros agregamos archivos en git antes de enviarlos al repositorio local con un ``commit``.

Pero para efectos prácticos simplemente vean lo como cosas distintas una cosa es "staging" dentro del desarrollo y otra cosa es ``staging`` dentro de git.

"Staging" Para el desarrollo son ramas que justo está antes de main y entonces aquí también tenemos un servidor pero este servidor también es nuestro server de pruebas, nosotros creamos una rama especial donde vamos a tener lo que sé que estemos desarrollando que es la rama de la característica, nosotros anteriormente creamos una para el ``header`` y otro para el ``footer`` y se desarrollan en el entorno local normal, y luego se envía una versión de esa rama a "staging" para hacerle un ``merge``  a la última versión de el "staging", en teoría "staging"  y ``main`` siempre deben estar actualizados esto es trabajo del líder de equipo, pero asumiendo que están actualizados esto normalmente le llamaríamos un ``merge``. Pero resulta que el ``merge`` no es la forma correcta de hacerlo en un entorno profesional hay que revisar el código, entonces esto va a un lugar intermedio que se conoce como ***pull request***.

***pull request*** es básicamente un estado intermedio antes de hacer el `merge` lo que el **pull request** me permite es que otros miembros del equipo puedan ver los cambios que tú hiciste, y si les gusta aprobarlos y al aprobarlo se auto ejecuta el `merge` al ``staging``  una vez la pruebas has testado en lo que quieres hacer es fusionar tus cambios con la rama main entonces haces también un **pull request**.

El **pull request** no es una característica de git es una característica de github, recordemos que GIF es la base de datos local que me permite hacer cambios granulares que me permite hacer ramas, tags, que me permitirá retroceder en el tiempo, que me ayuda nunca perder trabajo y entender toda la estructura de un proyecto, y trabajar colaborativamente pero github es el sitio web que me permite trabajar en conjunto con otros programadores de cualquier lugar del mundo o con otras personas, es el sitio que me permite ver en un solo lugar todos mis cambios, este **pull request**  es una característica exclusiva de github, también existe en gitlab simplemente que ellos le llaman distinto **merge request**, también existe en bitbucket pero ellos le llaman **push request** , esas son las opciones que se encuentran actualmente en el mercado pero el más común es el de github conocido como **pull request**, el cual es muy importante porque permite que personas que no sean colaboradores puedan trabajar y apoyar en una rama, ahora que lo tenemos todo claro vamos a hacer todo lo que dijimos, ahora bien generalmente los que uno en todo esto son un equipo muy especial que se llaman Dev Ops que es un administrador del entorno de desarrollo que hace que toda la vida del programador sea mucho más fácil y que el trabajo sea de una manera más productiva.

---

Imaginemos que en el ejercicio anterior tuviéramos 2 problemas, que serían errores de tipado en 2 palabras sin embargo esto no amerita seguir trabajando en nuestra rama pero podemos tener una barra especial para ello y luego lo podemos funcionar esto es a lo que se llama una buena práctica, lo que hacemos es un:

	  git full origin main

Para traernos la última versión de nuestro archivo, hecho esto vamos a crearnos una nueva rama que la vamos a llamar fix-typo:

	  git branch fix-typo

Qué sería para arreglar un error la palabra *typo* qué significa un error tipográfico en inglés, ya la rama está creada pero si tenemos las dudas simplemente hacemos: ``git branch`` y vemos la nueva rama que creamos.

Lo siguiente es hacer un:

	  git checkout fix-typo

Así podemos empezar a trabajar en la rama principal de fix-typo, Puedo ir a mi código y hacer ese cambio en los errores tipográficos.
Una vez realizados podemos hacer el cambio de ``git dif`` vamos a encontrar los cambios del cómo era al cómo está ahora entonces lo siguiente que tenemos que hacer es un: 

	  git push origin fix-typo

Antes de hacer el push tratemos de entender en dónde estamos, soy el dueño del repositorio y estoy viendo mi rama master, y estando seguro envío el ``push``, una vez hecho voy a la página de github y reviso, hoy encuentra la nueva rama creada fix-typo y me sale que hay un branch que está aparentemente combinado con master y ese branch en ese momento es un fix-typo , pero ahora cómo le hacemos para fusionarlo con el otro lado. Lo es que podemos crear un nuevo pulse request desde github y desde ahí le decimos que main lo compare con fix-typo hoy y ya que hice los cambios voy a hacer un ``git status`` en bash y me mostrara que efectivamente cambié el archivo, recordemos que todos los cambios que se hagan hay que agregarles y hacerles un commit:

  	git commit -am "Typos arreglados en el post"

Ahora sí vamos a hacer un:

  	git push origin fix-typo
	
Ahora sí vamos a github el cual nos va a decir que tenemos una diferencia entre la rama fix-typo  y la main, no quiere hacer una comparación y un pull request, entremos a new pull request si yo soy el dueño del repositorio y estoy en la rama main entonces le doy new full request Neva a decir que tengo una rama main y tengo otra rama que quiero comprar entonces hacemos la comparación de la rama fix-typo entonces se puede hacer una fusión y los cambios se pueden hacer automáticamente.  Pero podemos ver como se hacen automáticamente vamos a compair new request y ahí estará, lo que nos permite al hacer esto es agregarle detalles entonces se puede por ejemplo mirando más abajo los cambios que se realizaron en la corrección de los eso es tipográficos si vemos más arriba nos mostrará el nombre del commit que hicimos y en el recuadro nos permitirá agregar un mensaje "No debimos pasar este error a main." lo que indicaría que cometimos un error, hoy se puede agregar personas para que revisen esto en el recuadro de la derecha el apartado *Reviewers* son personas con la que estamos trabajando actualmente en este caso como ejemplo tenemos a Anita y haciendo esto es como decirle Anita puedes revisar este pull request?, también le puedo asignar este pull quest a alguien o colocarle un label que son etiquetas, esto es muy útil en el proceso de Dev Ops qué es el proceso de crear un sistema en el cual nosotros como programadores podemos trabajar mejor.

Milestone significa que teníamos un objetivo Que teníamos y que este pulso y cuesta lo representa y el apartado de Projects es como forma de agrupar repositorios desde dentro de github, esto no entra tanto a github como herramienta sino a formas de trabajo Dev Ops.

El pull request es no ejecuta el merge de por sí, Simplemente describe que es lo que está pasando y alguien del equipo revisarlo y ejecutarlo, lo importante es enviarlo al equipo entonces nosotros hacemos clic en create pull request y al crear ese pull request lo que estoy haciendo es decirle a alguien el mensaje que escribimos en el recuadro:  "No debimos pasar este error a main.".

Entonces veamos esto desde la perspectiva del colaborador:

la cual Anita entra a su github y puede ver que hay un pull request. Entonces ella al darle clic encontramos que hay un mensaje de typos arreglados en el post, al hacerle clic se puede ver qué es lo que está pasando y nos dice que el dueño del repositorio está pidiendo tú revisión de este pull request, es decir hacer una revisión de esos cambios, porque el dueño quiere fusionar un main con su rama fix-typo, entonces lo puedo leer y puedo entender que pidió el request y que la rama no tiene conflictos actualmente nosotros podríamos ir al botón de Merge pull request y podemos ver otras opciones como create squash y rebase and merge, nosotros simplemente haremos un merge sin embargo agregar que tanto el squash como el rebase se consideran mala práctica.

Ahora podemos ver la opción de commits y ver qué es lo que cambió, entonces nos muestra el mensaje de commit, porque un pull request puede ser un commit commits, porque puede ser una rama entera en la que cambió, en este caso es muy sencillo y podamos revisar qué cambios fueron realizados, y digamos que no lo vamos a aceptar entonces vemos la opción de review changes y vemos 3 opciones la cual sería comments que sería comentarlo approve que sería aprobarlo o request changes.

Si nosotros hacemos el approve sería aprobarlo y hacer el merge, oh pedirle cambios request changes y los cambios que se va a pedir es: "en lugar de utilizar tildes directas, usar entidades html" y con esto sabemos que se va a enojar el dueño del repositorio pero así es la vida.

Ahora como dueño del repositorio entro a github y veo que tengo un mensaje normal y veo esa notificación que aparentemente es qué tengo algo en rojo y Anita hoy me está pidiendo que haga cambios, entonces no se pueden hacer cambios todavía no es posible hacer un `merge` porque nos indica que "en lugar de utilizar tildes directas, usar entidades html", está bien digamos que respeto su opinión y voy a trabajar entonces codificaremos:

	  gits pull origin fix-typo 

Con esto actualizamos el repositorio y procedemos a hacer el cambio que nos pidió entonces vamos donde teníamos el error de tipado y cambiamos los errores de tildes por entidades html.
	
	  git commit -am "Cambio a entidades html en lugar de tildes"

Ahora hacemos un:

	  git push origin fix-typo

Como dueño del repositorio puedo volver a github y revisar mi rama fix-typo donde simplemente podemos verificar si es que todo está bien y revisar si se repararon los errores de tipado. 

Si Vamos hacia atrás podemos ver un view#1 que sería básicamente el pull request que ya se había ejecutado, el pull  request no cambia realmente, si nosotros nos fijamos los cambios fueron pedidos pero ya fueron hechos entonces podemos empezar una conversación porque ya tenemos 2 pull request acá y escribimos: "Cambio a entidades html hecho, por favor hazme el merge", presionamos comment.

Cómo Anita está revisando su mensaje en GitHub vemos todos los mensajes y vemos los últimos cambios, entonces notamos que se hicieron los cambios por entidades html, entonces click en revisar los cambios *Review chances* Y escribir un mensaje en el recuadro: "Excelente. Eso era!"

Entonces aprobamos los cambios: Submit review, eso significa que los cambios están aprobados, aunque los cambios estén aprobados no significa que él merge se haya ejecutado, solo significa que viewer ya tiene un check que quiere decir que aprobó los cambios, pero alguien tiene que tomar la decisión de hacer un merge, pero como Anita es colaboradora en este proyecto puede hacer un merge y fusionar esto con el main, claro que lo importante es que se respete quién hace los merge, porque ahora no existe un proceso de Code Review y esto es una excelente práctica, vamos a darle un pull request y para hacer el merge request debemos hacer lo siguiente:

	  Merge pull request #1 from admin/fix-typo

Y con eso ya estaría, nos saldrá el siguiente mensaje:

	  pull request  succesfully merged and closed

Esto es interesante por qué puedo borrar la rama, hacer eso significa que como todo esto era un fix de última hora de pronto no lo necesito para poder liberarme de ramas, entonces esto depende del Modo de práctica de cada empresa, puede que tú quieras hacer eso pero que la empresa no lo permita, sin embargo en este caso como es un ejemplo nosotros colocaremos delete branch y con eso ya está, ahora si vamos a nuestro hyperblog y cambiamos a la rama main. Miro mi documento html efectivamente veremos los cambios que se hicieron con entidades y podamos ver todo lo que se hizo en github.

Bueno ahora qué pasa si tú no eres un colaborador del proyecto, y quieres aportar algo digamos a un proyecto open source como ahí los pull request  son aún más importantes porque tú ahí merge ahí lo que se hace es coronar haciendo un ``fork`` y luego hacer un pull request de una manera ligeramente distinta.


