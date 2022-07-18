# _Jenkins_

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/jenkins01-removebg-preview.png)

---

Para validar una buena explicación de como trabajar con jenkins se puede valiar esta [pagina](https://dmunozfer.es/tutorial-jenkins-2-configuracion-pipeline/)

Otro video en ingles con el setup y con toda la configuración en general se puede consultar este [video tutorial](https://www.youtube.com/watch?v=nCKxl7Q_20I&t=11s)

---

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

# Jenkins CLI JAR

- Esto aplica para manejar Jenkins desde una terminal,

En la version de escritorio de jenkins de manera local vamos a la pagina:

```url
http://localhost:8080/cli/
```

Luego se descarga el complemento destinado para esta acción:

```url
http://localhost:8080/jnlpJars/jenkins-cli.jar
```

Cuando se tiene el .jar descargado en la maquina de forma local, lo que se debe hacer es en la terminal agregar el link que nos propone jenkins en la misma pagina.

- Ejemplo:

```shell
$ cd Downloads
$ cd java -jar jenkins-cli.jar -s http://localhost:8080/ -webSocket help
```

El resultado por consola es algo parecido a esto:

```shell
cd Downloads
❯ java -jar jenkins-cli.jar -s http://localhost:8080/ -webSocket help
  add-job-to-view
    Adds jobs to view.
  build
    Builds a job, and optionally waits until its completion.
  cancel-quiet-down
    Cancel the effect of the "quiet-down" command.
  clear-queue
    Clears the build queue.
  connect-node
    Reconnect to a node(s)
  console
    Retrieves console output of a build.
  copy-job
    Copies a job.
  create-credentials-by-xml
    Create Credential by XML
  create-credentials-domain-by-xml
    Create Credentials Domain by XML
  create-job
    Creates a new job by reading stdin as a configuration XML file.
  create-node
    Creates a new node by reading stdin as a XML configuration.
  create-view
    Creates a new view by reading stdin as a XML configuration.
  declarative-linter
    Validate a Jenkinsfile containing a Declarative Pipeline
  delete-builds
    Deletes build record(s).
  delete-credentials
    Delete a Credential
  delete-credentials-domain
    Delete a Credentials Domain
  delete-job
    Deletes job(s).
  delete-node
    Deletes node(s)
  delete-view
    Deletes view(s).

```

Desde esta parte ya es posible realizar una ejecución del proyecto desde la terminal usando el archivo .jar

En la misma pagina es posible tener el comando de ejecución por la terminal para el proyecto actual.

Este seria le comando.

```shell
$ java -jar jenkins-cli.jar -s http://localhost:8080/ build <<Nombre del proyecto>>
```

El comando especifico queda de la siguiente forma:

```shell
$ java -jar jenkins-cli.jar -s http://localhost:8080/ build fsbp_api_automation_rest_assured
```

**Nota**: en la consola no se debe ver ningún output.

---

En esta parte se realiza la ejecución del proyecto desde la consola y es posible ver la ejecución desde jenkins.

```text
Success
TestNG Reports Processing: START
Looking for TestNG results report in workspace using pattern: /Users/andresrios/Documents/AndresRios/fsbp/fsbp_api_automation_rest_assured/testng-results.xml
Did not find any matching files.
[Slack Notifications] found #78 as previous completed, non-aborted build
[Slack Notifications] will send OnSuccessNotification because build matches and user preferences allow it
Finished: SUCCESS
```

# Como lanzar un proyecto desde otro proyecto:

Como ya se tiene un proyecto corriendo y se requiere lanzar ese proyecto desde uno nuevo lo que se hace es lo siguiente:

1. Se crea el nuevo proyecto
2. En configuración se selecciona la pestaña de Post-build Actions
3. En Projects to build se agrega el proyecto a correr desde este
4. Se selecciona la opción Trigger only if build is stable
5. Click en Guardar
6. Se ejecuta el proyecto desde Build Now
7. Se valida que la ejecución sea generada.
