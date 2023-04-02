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

Este `pull` nos traerá los *cambios del remoto* , por lo que se estará al día en el proyecto, el flujo de trabajo cambia, en adelante se estará  trabajando haciendo **pull request**desde el app stream y **push al origin**. Para pasar a hacer **pull request**

    git pull upstream main

    git push origin main



