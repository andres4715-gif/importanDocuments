## Dada la clase personas:

```shell
package javaPractice.stream.entendiendoStreams;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

import java.time.LocalDate;

@Data
@AllArgsConstructor
@NoArgsConstructor
public class Person {
    private int id;
    private String name;
    private LocalDate birthday;
}
```

## Dada la clase Productos:

```shell
package javaPractice.stream.entendiendoStreams;


import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

@Data
@AllArgsConstructor
@NoArgsConstructor
public class Product {
    private int id;
    private String name;
    private double price;
}
```

## Dada la clase main() con los objetos de las clases person y product creados

```shell
package javaPractice.stream.entendiendoStreams;

import java.time.LocalDate;
import java.time.Period;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

// Esto esta en el proyecto
// selenium_4
// En la ruta: src/main/java/javaPractice/stream/entendiendoStreams

public class App {

    public static void main(String[] args) {

        Person p1 = new Person(1, "Andres", LocalDate.of(2003, 1, 21));
        Person p2 = new Person(2, "Jorge", LocalDate.of(2000, 3, 23));
        Person p3 = new Person(3, "Estevan", LocalDate.of(1960, 2, 11));
        Person p4 = new Person(4, "Liliana", LocalDate.of(1979, 4, 3));
        Person p5 = new Person(5, "Camilo", LocalDate.of(1980, 5, 22));

        Product prod1 = new Product(1, "ceviche", 34.6);
        Product prod2 = new Product(2, "galleta", 34.6);
        Product prod3 = new Product(3, "chocolatina", 34.6);
        Product prod4 = new Product(4, "mandarina", 34.6);

        List<Person> persons = Arrays.asList(p1, p2, p3, p4, p5);
        List<Product> products = Arrays.asList(prod1, prod2, prod3, prod4);

```

## Es posible iniciar a jugar con las listas o colecciones con los diferentes metodos

## Metodo Match (param : predicate)

- Es una operación de flujo intermedio y se puede utilizar de la siguiente forma:

* anyMatch
* allMatch
* noneMatch

- La operación principal del Match es retornar un booleano (True or False) para poder tomar decisiones con este resultado.

```shell
Ejemplo 1: anyMatch

En este lo que se quiere validar es si dada la lista de personas que tenemos previamente
tenemos por lo menos un dato que inicia con la letra (L) si en la lista se tiene un dato
que inicia con la letra (L) nos va a retornar un true y en caso contrario nos retorna false

- Se puede ver en el ejemplo que no vamos a retornar una lista, solo vamos a retornar un dato boolean.

- Para este especifico, el anyMatch no recorre toda la lista. el simplemente busca que se tenga por lo
menos un dato que cumpla la condición y si encuentra por lo menos un match con eso nos da el true


        boolean rpta1 = persons
                .stream()
                .anyMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta1);

* El output despues de ejecutar va a ser true or false dependiendo si se cumple o no la condición
y con este resultado vamos a podemos seguír avanzando en el programa.

Para este ejemplo la salida fue true

```

```shell
Ejemplo 2: allMatch

- Para el allMatch todos los datos deben coincidir, en este caso tenemos una lista de nombres y esto
implica que al no coinidir la primera letra en todas las iteraciones el va dar como salida un false


        boolean rpta2 = persons
                .stream()
                .allMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta2);

* El output despues de ejecutar va a ser false ya que no se cumple con la condición del allMatch
en todas las iteraciones.
```

```shell
Ejemplo 3: noneMatch

- Para el noneMatch si vamos a trabajar con una lista de personas se debe evaluar cada uno de los
datos que se obtienen de la lista, es este caso vamos a evaluar si alguno de los nombres inicia
con la letra ("L") y como efectivamente hay un dato que es (Liliana) el debe retornar un false


        boolean rpta3 = persons
                .stream()
                .noneMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta3);

* Cambiando de ejemplo si buscamos con letra ("X") En toda la lista se va a encontrar que no se
tiene nunguna coincidencia y esto hace que el output sea true

        boolean rpta3 = persons
                .stream()
                .noneMatch(x -> x.getName().startsWith("X"));
        System.out.println(rpta3);
```
