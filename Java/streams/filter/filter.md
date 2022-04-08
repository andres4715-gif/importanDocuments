# _Ejemplo 1_:

# Dada la clase personas:

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

## Metodo Filter (param : predicate)

- Predicate: Lo que significa es que retorna un booleano (true or false)
  para poder seguir avanzando y obtener la lista que se quiere obtener. claro esta que no es necesario que sea un booleano, solo es un paso que nos permite seguir avanzando a obtener el resultado que queremos para continuar con el flufo que queremos.

- El metodo filter nos crea un nuevo ArrayList para contitnuar trabajado y no afectar el ArrayList que ya tenemos:

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

---

# _ejemplo2:_

- Data la clase modelo:

```java
import lombok.AllArgsConstructor;
import lombok.Data;

@Data
@AllArgsConstructor
public class Usuarios {

    private String nombre;
    private String apellido;
    private Integer edad;
    private String sexo;
}
```

- Data la clase intermedia:

```java
import java.util.ArrayList;
import java.util.List;

public class StepDefinition {

    public static void checkig() {

        List<Usuarios> user = new ArrayList<>();
        user.add(new Usuarios("Andres", "Rios", 45, "M"));
        user.add(new Usuarios("Oscar", "Quintero", 40, "M"));
        user.add(new Usuarios("Viviana", "Hernandez", 3, "F"));
        user.add(new Usuarios("Carmen", "Urrea", 12, "F"));

        user.stream()
                .filter(x -> x.getEdad() <= 30)
                .forEach(x -> System.out.println(x.getNombre()));
    }
}
```

- Dada la clase main

```java
public class Main {

    public static void main(String[] args) {

        StepDefinition.checkig();
    }
}
```

- Se obtiene el output:

Viviana

Carmen
