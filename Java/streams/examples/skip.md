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

## Metodo Skip

- Permite omitir algún datos o datos para iniciar despues de un lugar en la lista determinado.

```shell

Ejemplo 1:

* Si requiero omitir los primeros 2 datos de la lista y crear una nueva lista de personas.
- En este caso la nueva lista debe retornar los datos de la lista omitiendo los primeros
dos datos de esta

- En el codigo seria:

        List<Person> filteredList4 =  persons
                .stream()
                .skip(2)
                .collect(Collectors.toList());
        App.printList(filteredList4);

        }

            public static void printList(List<?> list) {
                list.forEach(System.out::println);
            }

- El output seria la lista de personas omitiendo los dos primeros datos de la lista

Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=4, name=Liliana, birthday=1979-04-03)
Person(id=5, name=Camilo, birthday=1980-05-22)
```
