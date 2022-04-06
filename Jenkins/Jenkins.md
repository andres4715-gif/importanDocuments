# _Jenkins_

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/jenkins01-removebg-preview.png)

Link con el [video](https://www.youtube.com/watch?v=woMAXn4e8NA&t=1093s)
Page para saber la [Configuración](https://blog.kobiton.com/integrating-appium-tests-into-your-ci/cd-process-using-jenkins) para maven en Jenkins.

## Ejecutar jenkins desde la Terminal CLI

- Como ejemplo de toma el proyecto de _Firestone API_

1. Tener instalado Jenkins
2. Para correr Jenkins se corre el comando en una terminal y se deja ejecutando.

```shell
 $ jenkins-lts
```

Despues que Jenkins este activo por http://localhost:8080/
es posible descargar la consola CLI.

La ruta para la descarga de la consola es:

```text
Manage Jenkins/ Jenkins CLI
```

En dicah pantalla se muestra algo como esto donde es posible descargar el .jar:

```text
Jenkins CLI
You can access various features in Jenkins through a command-line tool. See the documentation for more details of this feature. To get started, download jenkins-cli.jar, and run it as follows:
```

Ya con el jar Descargado en una nueva ventana de la terminal es posible ejecutar el proyecto que se requiera, para este ejemplo se ejecutara el proyecto de build FirestoneAPITesting

NOTA: Buscar la ruta donde esta descargado el .jar y despues agregar el siguiente comendo.

```shell
$ java -jar jenkins-cli.jar -s http://localhost:8080/ build FirestoneAPITesting
```

Al ejecutar no se debe mostrar ningún tipo de error y se podra ver el resultado de la ejecución.

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/jenkins2.png)

- Si se requiere mas detalle se le puede agregar a la linea de comando la letra (s) y de esa forma el comando quedaria de la siguiente forma:

```shell
$ java -jar jenkins-cli.jar -s http://localhost:8080/ build FirestoneAPITesting -s
```

- El resultado de la ejecución debe mostrar algo como esto:

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/jenkins3.png)

- Como se puede ver la ejecución es la numero 7 y debe ser la misma que se ejecuto en el dashboard en la pagina inicial de jenkins

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/imagen%204.png)
