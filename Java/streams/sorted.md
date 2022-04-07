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

## Metodo Sorted:

- Teniendo en cuenta la Clase personas, la clase Productos y la Clase App
  donde se tiene las colecciones (Listas). se puede optar por organizar los resultados para que estos queden organizados de la forma que se requiera.

Teniendo en cuenta que se tiene la lista de personas y se quiere tener dicha lista organizada de forma ascendente, esto se puede obtener con la programación funcional de la siguiente forma :

```shell

Ejemplo 1:

Lo primero que se debe tener en cuenta es que vamos a requerir una Lista<String>
ya que el dato name es de tipo <String> y vamos a trabajar con la lista (persons) a dicha
colección se el aplica el metodo .stream(), luego el metodo .map() para obtener los nombres,
luego el metodo .sorted() ya en esta parte se tiene la lista de nombres organizada de la forma que queremos.

    List<String> filteredList3 = persons
            .stream()
            .map(p -> p.getName())
            .sorted()
            .collect(Collectors.toList());
        App.printList(filteredList3);

- La lista de nombres real es de esta forma:

Andres
Jorge
Estevan
Liliana
Camilo

- Pero despues de aplicar el metodo .sorted() el resultado por consola que se obtiene es:

Andres
Camilo
Estevan
Jorge
Liliana

```

```shell

Ejemplo 2:

Hacer lo mismo pero con un objeto completo:

- Ahora la necesidad es ordenar no solo los nombres si no que ahora se requiere ordenar por nombre pero
la lista completa, osea el objeto completo

Para poder hacer esto es necesario decirle al metodo .sorted()
por parametro como se quiere organizar el objeto. esto se logra
a traves de un comparator que lo veremos a continuación:

        // sorted(param : comparator)
        // Comparator<persons>

        Comparator<Person> byNameAcs = (Person o1, Person o2) -> o1.getName().compareTo(o2.getName());
        List<Person> filteredList4 = persons
                .stream()
                .sorted(byNameAcs)
                .collect(Collectors.toList());
        App.printList(filteredList4);
    }

        public static void printList(List<?> list) {
        list.forEach(System.out::println);
    }

El output de salida seria de la siguiente forma:

Person(id=1, name=Andres, birthday=2003-01-21)
Person(id=5, name=Camilo, birthday=1980-05-22)
Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=2, name=Jorge, birthday=2000-03-23)
Person(id=4, name=Liliana, birthday=1979-04-03)


- En caso de querer hacerlo de forma descendente solo seria cambiarle el orden al Comparator y el codigo
quedaria de la siguiente forma:

        // Comparator<persons>

        Comparator<Person> byNameDesc = (Person o1, Person o2) -> o2.getName().compareTo(o1.getName());
        List<Person> filteredList4 = persons
                .stream()
                .sorted(byNameDesc)
                .collect(Collectors.toList());
        App.printList(filteredList4);
    }

        public static void printList(List<?> list) {
            list.forEach(System.out::println);
        }
}

El output de salida seria de la siguiente forma:

Person(id=4, name=Liliana, birthday=1979-04-03)
Person(id=2, name=Jorge, birthday=2000-03-23)
Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=5, name=Camilo, birthday=1980-05-22)
Person(id=1, name=Andres, birthday=2003-01-21)
```
