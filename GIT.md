# _GIT_

- Agregar Tu Nombre y Correo Electrónico

```shell
git config --global user.name "Mi Nombre"
git config --global user.email "micorreo@ejemplo.com"
```

- Para deshacer un git add antes de un commit, ejecuta

```shell
$ git reset <archivo>
$ git reset para deshacer todos los cambios.

Ejemplo:

git reset src/test/java/com/wizeline/app/AppTest.java
```

- Para tener documentación de algún comando en consola:

```shell
Ejemplo:

$ git help commit
```

- Como ver todo el historial de commits de un proyecto:

```shell
- Para ver todo el historico del proyecto solo es agregar el siguiente comando:

$ git reflog
```

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

- Para ver todo el historial con graficos

```shell

El comando a utilizar para esto es:
$ git log --oneline --decorate --all --graph


```
