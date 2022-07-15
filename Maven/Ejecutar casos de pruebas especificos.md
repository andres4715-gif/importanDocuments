# Lanzar un único test con Maven

Cuando tenemos varias clases de test con JUnit y queremos lanzar con maven un único test podemos escribir por linea de comandos lo siguiente:

```shell
$ mvn test -Dtest=NombreDelTest
```

Nota: No hay que poner el paquete, únicamente el nombre del test.

Si queremos ir a grano más fino y queremos ejecutar un único test incluido en una clase de test deberemos especificar el método de la siguiente forma:

```shell
mvn test -Dtest=NombreDelTest#NombreDelMetodo
```

Ejemplos:

```shell
$ mvn test -Dtest=Get_Documents_Search
$ mvn test -Dtest=Get_Documents_Search#checkStatusCodeWithOutParams_us
```

Para mayor información consulta la [fuente](http://maven.apache.org/general.html#run-one-test) oficial
