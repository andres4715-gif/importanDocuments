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

## Metodo Limit

- Permite tomar de la lista de datos los que se requieran iniciando desde el dato (0) en la lista.

```shell

Ejemplo 1:

* La lista de personas tiene 5 Personas dentro de ella y se requiere solo tener dos datos de la lista.

- En el codigo seria:

        List<Person> filteredList5 =  persons
                .stream()
                .limit(2)
                .collect(Collectors.toList());
        App.printList(filteredList5);
    }

            public static void printList(List<?> list) {
                list.forEach(System.out::println);
            }

- El output seria la lista de personas omitiendo los dos primeros datos de la lista

Person(id=1, name=Andres, birthday=2003-01-21)
Person(id=2, name=Jorge, birthday=2000-03-23)

```
