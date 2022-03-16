# _Maven_

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/apache_maven_l5hy2n.png)

## Para la [instalación](https://www.youtube.com/watch?v=biBOXvSNaXg&list=PLvimn1Ins-40atMWQkxD8r8pRyPLAU0iQ&index=2) de maven en Windows, linux o Mac

## [Documentación](https://maven.apache.org/guides/getting-started/index.html) oficial de Maven:

- Primero que todo siempre buscar la forma de importar los proyectos en el IDE como proyectos tipo maven es decir no como proyectos java normales

## Comandos:

```shell
$ maven clean: Limpia la carpeta target


```

## Crear un nuevo proyecto de maven desde la consola:

- Crear una carpeta en alguna ruta de la maquina:

```shell
$ cd /Users/andresrios/Desktop/NewMavenProject
```

- Para crear el archetype del proyecto se puede tomar este ejemplo, en la ruta del proyecto en la consola se debe agregar el siguiente comando:

```shell
$ mvn -B archetype:generate -DgroupId=com.wizeline.app -DartifactId=my-app-wizeline-practice -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4
```

- Explicación de la linea de comandos:

```shell
-> mvn -B archetype:generate: Disponible en las ultimas versiones y es para crear el archetype

-> -DgroupId=com.wizeline.app: Es sobre la estructura que va a tener el proyecto

-> -DartifactId=my-app-wizeline-practice: Es el nombre del proyecto

-> -DarchetypeArtifactId=maven-archetype-quickstart: Para crear un proyecto web pero puede tomar el valor que sea requerido.
```

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/Screen%20Shot%202022-03-16%20at%2012.10.23%20PM.png)

- Con el proyecto creado lo que se hace es por linea de comandos ingresar en la carpeta del proyecto el siguiente comando:

- Esto lo que hace es crear la carpeta target en el proyecto:

```shell
$ mvn compile
```

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/Screen%20Shot%202022-03-16%20at%2012.14.50%20PM.png)

- Despues de añadir el comando mvn compile se puede la nueva estructura del proyecto:

![Image text]()
