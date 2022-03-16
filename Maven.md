# _Maven_

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/apache_maven_l5hy2n.png)

## Para la [instalación](https://www.youtube.com/watch?v=biBOXvSNaXg&list=PLvimn1Ins-40atMWQkxD8r8pRyPLAU0iQ&index=2) de maven en Windows, linux o Mac

## [Documentación](https://maven.apache.org/guides/getting-started/index.html) oficial de Maven:

- NOTA: Con Maven se pueden crear los .jar para [saber](https://www.youtube.com/watch?v=4OhwsOxYJWc&list=PLvimn1Ins-40atMWQkxD8r8pRyPLAU0iQ&index=3) como se crea el ejecutable del proyecto se pude ver el video.

- NOTA: Tener en cuenta que es posible tener mas de un archivo POM en el mismo proyecto y solo es saber cual se quiere utilizar, se puede ver en este [video](https://www.youtube.com/watch?v=zFcD8cqLFmo&list=PLvimn1Ins-40atMWQkxD8r8pRyPLAU0iQ&index=8)

- Primero que todo siempre buscar la forma de importar los proyectos en el IDE como proyectos tipo maven es decir no como proyectos java normales

## Comandos:

```shell
$ mvn clean: Limpia la carpeta target
$ mvn install: Es para instalar las dependencias de forma local y eso permite que se puedan utilizar en otro proyecto


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

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/Screen%20Shot%202022-03-16%20at%2012.19.19%20PM.png)

# _POM_

Archivo en xml (Project Object Model)

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.wizeline.app</groupId>
    <artifactId>my-app-wizeline-practice</artifactId>
    <version>1.0-SNAPSHOT</version>

    <name>my-app-wizeline-practice</name>
    <!-- FIXME change it to the project's website -->
    <url>http://www.example.com</url>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.source>8</maven.compiler.source>
        <maven.compiler.target>8</maven.compiler.target>
    </properties>

    <dependencies>
        <!-- https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java -->
        <dependency>
            <groupId>org.seleniumhq.selenium</groupId>
            <artifactId>selenium-java</artifactId>
            <version>4.1.0</version>
        </dependency>

        <!-- https://mvnrepository.com/artifact/org.testng/testng -->
        <dependency>
            <groupId>org.testng</groupId>
            <artifactId>testng</artifactId>
            <version>7.4.0</version>
            <scope>test</scope>
        </dependency>

        <!-- https://mvnrepository.com/artifact/io.github.bonigarcia/webdrivermanager -->
        <dependency>
            <groupId>io.github.bonigarcia</groupId>
            <artifactId>webdrivermanager</artifactId>
            <version>5.1.0</version>
        </dependency>


        <!-- https://mvnrepository.com/artifact/org.projectlombok/lombok -->
        <dependency>
            <groupId>org.projectlombok</groupId>
            <artifactId>lombok</artifactId>
            <version>RELEASE</version>
            <scope>compile</scope>
        </dependency>
    </dependencies>
</project>

```

# _Saber un poco mas sobre el archivo POM y las properties para cambios de ambiente dependiendo de la ejecucion requerida._

- Atributos personalizados
- Los usuarios pueden personalizar las propiedades de Maven bajo los elementos de POM

- Se puede ver el siguiente [video](https://www.youtube.com/watch?v=s7boC0U4iew&list=PLvimn1Ins-40atMWQkxD8r8pRyPLAU0iQ&index=7) para saber como se pueden configurar los ambientes con archivos .properties esto se configura con el archivo runner en el IDE y se podria correr en diferentes ambienes

```xml
 <! - Versión dependiente de la configuración ->
 <properties>
     <!-- Environment Settings -->
     <java.version>1.8</java.version>
     <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
     <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>

     <!-- Spring cloud Settings   -->
     <spring-cloud.version>Finchley.RELEASE</spring-cloud.version>
     <spring-boot-admin.version>2.0.1</spring-boot-admin.version>
     <zipkin.version>2.10.1</zipkin.version>
 </properties>

```
