# _GIT_

- Paginas de consultas rapidas

[Descartar cambios de archivos con Git](https://desarrolloweb.com/articulos/descartar-cambios-archivos-git.html)

[Git Stash Explicado](https://www.freecodecamp.org/espanol/news/git-stash-explicado/)

[Borrar ramas locales y desde el origin](https://www.hostinger.es/tutoriales/renombrar-rama-git)

---

- Agregar Tu Nombre y Correo Electrónico

```shell
git config --global user.name "Mi Nombre"
git config --global user.email "micorreo@ejemplo.com"
```

---

- Para deshacer un git add antes de un commit, ejecuta

```shell
$ git reset <archivo>
$ git reset para deshacer todos los cambios.

Ejemplo:

git reset src/test/java/com/wizeline/app/AppTest.java
```

---

- Para cambiar el nombre de una rama local
  Desde la rama que le que se le quiere cambiar el nombre se aplica el sig comando:

```shell
$ git branch -m new-name
```

Por otro lado si el nombre de la rama que se quiere cambiar lo vamos a hacer desde

otra rama, se debe aplicar el sig comando:

```shell
$ git branch -m old-name new-name
```

---

- Para tener documentación de algún comando en consola:

```shell
Ejemplo:

$ git help commit
```

---

- Como ver todo el historial de commits de un proyecto:

```shell
- Para ver todo el historico del proyecto solo es agregar el siguiente comando:

$ git reflog
```

---

- Cambiar el nombre al ultimo commit realizado por algún error en la escritura

```shell

Ejemplo:

$ git commit --amend -m <"nuevo nombre del commit">

Esto modificara el nombre del commit realizado anteriormente.

Se puede validar el cambio del nombre con el comando:

$ git log

Console:

commit 0f6629f7ce767fb4f41e2f546aef34b7cea6b713 (HEAD -> master)
Author: Andres Rios <69942140+andres4715-gif@users.noreply.github.com>
Date:   Fri Mar 18 09:15:12 2022 -0500

    <"adding mistake 3">
```

---

- Para eliminar un archivo cuando necesitamos que quede el registro de la eliminación

```shell
$ git rm <"Nombre del archivo">

Ejemplo:

$ git rm src/test/java/com/wizeline/app/ToBeRemoved.java

Git en ese momento borra el archivo del proyecto y lo almacena en el historial.

Luego de ser borrado el archivo del proyecto de debe agregar los comandos:

$ git add .
$ git commit

Pero que pasa si es necesario recuperar ese archivo que se elimino:
Con el id del commit por ejemplo: cadb9d45c9643a4cb157357f9a30f9df92750f1d se puede recuperar con el siguiente comando:

$ git reset --hard cadb9d45c9643a4cb157357f9a30f9df92750f1d
```

---

- Para ver todo el historial con graficos

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/Screen%20Shot%202022-03-18%20at%2011.11.43%20AM.png)

```shell

El comando a utilizar para esto es:
$ git log --oneline --decorate --all --graph
```

---

- Para borrar una rama que de forma local:

```shell
- El comando para borrar una rama debemos estar una rama diferente
de la rama que se requiere borrar y el comando es:

$ git branch -d <"Nombre de la rama a eliminar">
```

---

- GIT STASH

En este [link](https://www.freecodecamp.org/espanol/news/git-stash-explicado/) Esta toda la documentación sobre los Stash

```shell
- Guardar cambios en el stash

$ git stash save "mensaje opcional para ti"

- Ver los cambios guardados en el stash

$ git stash list

- Recuperar Cambios en Stash

$ git stash apply NOMBRE-DEL-STASH -> aplica los cambios y deja una copia en el stash

$ git stash pop NOMBRE-DEL-STASH -> aplica los cambio y elimina los archivos del stash

- Borrar los Cambios Guardados en Stash

$ git stash drop NOMBRE-DEL-STASH

- Para limpiar todo del stash, ejecuta el comando:

$ git stash clear
```

- # it rebase -> git squash

```shell
Desde la rama que estoy trabajando, esto es para descargar la ultima
version de la app ya que puede tener cambios (esto es mejor hacerlo
siempre si se trabaja con alguien mas)

$ git pull --rebase origin <LA RAMA DONDE NACIO MI RAMA>

* NOTA:  Esto es para traer la ultima version que se tenga en la rama principal  y cuando llega a nuestra rama ya tiene
un commit (No es necesario hacer un nuevo comit) en caso de tener conflictos se debe solucionar.

* NOTA2: En caso de tener la funcionalidad lista un nuestra rama se puede hacer el pull request sin problema
ya que no debe tener confictos

* NOTA3: Despues de tener el pull request listo ya los cambios estan en el origin (nube) en ese caso, si se quiere
ver los cambios en la rama local se debe se debe hacer con este comando:

$ git pull origin master

____________________________________

- Con un git logline se puede ver los commits que hay que hacerles el squash por que puede tener mas
commits de otras personas.

$ git rebase -i HEAD~<CANTIDAD DE COMMITS IDENTIFICADOS>

Se muestra una ventana con todos los commits que se tienen, se deja el primero
como esta osea con <p> y los otros se cambia por <s>

Se deja el comment que se quiera dejar ya que con este nombre va a quedar el unico commit y
este es el que van a aprobar despues de hacer el pull request.

$ git push origin <MI RAMA EN LA QUE TRABAJE> --force

En este punto se puede mirar en el repositorio que todos los commits son comprimidos en uno inclusive se puede
presentar que se tenga commits de otros pero esos no nos importan por que eso ya estaba en la rama ppal.
```
