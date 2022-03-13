## _STREAMS_

- La documentación se puede ver en esta [Pagina](https://www.youtube.com/watch?v=U5oOdNG2XQY)

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

        Person p1 = new Person(1, "Andres", LocalDate.of(2001, 1, 21));
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

### Se puede imprimir la lista con un metodo forEach tradicional de esta forma:

```shell

- Para recorrer las listas con un foreach

        for(Person myDataPerson : persons){
            System.out.println(myDataPerson);
        }

        for(Product myDataProduc : products){
            System.out.println(myDataProduc);
        }

```

### Para ejecutar lo mismo pero con un forEach mas simplificado:

- Esto es lo que se le llama (Expresion Lambda).

```shell
        persons.forEach(person -> System.out.println(person));

        products.forEach(product -> System.out.println(product));

- Pero se puede simplificar mas aún. Java dice que si el paremetro de la izquierda es el mismo que la derecha.

- Se pude declarar de esta forma.

        persons.forEach(System.out::println);
        products.forEach(System.out::println);

```

## Metodo Filter (param : function)

```shell

Ejemplo:

        List<Person> filteredList = persons
                .stream()
                .filter(p -> App.getAge(p.getBirthday()) >= 40)
                .collect(Collectors.toList());
        App.printList(filteredList);
    }

    public static int getAge(LocalDate birthDate) {
        return Period.between(birthDate, LocalDate.now()).getYears();
    }

    public static void printList(List<?> list) {
        list.forEach(System.out::println);
    }

- Con el filtro aplicado, se obtiene una nueva lista dondde se cumple la condición.

- En el output se puede ver esto como resultado:

Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=4, name=Liliana, birthday=1979-04-03)
Person(id=5, name=Camilo, birthday=1980-05-22)
```