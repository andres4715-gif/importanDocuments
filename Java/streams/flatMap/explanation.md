# _Como trabajar con FlatMap_

- La idea principal de flatMap es:
  Poder iterar y utilizar la API Stream para trabajar con objetos.

- Diferencia entre Map y FlatMap:

* Map itera en cada uno de los objetos de la colección por el contrario FlatMap itera en cada uno de los objetos.
* Este retorna multiples values como Objetos de un Stream

NOTA: Despues de haber realizado un FlatMap se puede trabajar de forma individual con los elementos ya que en ese punto ya
se ha trabajado con el grupo de objetos.

El stream lo que retorna es un stream de objetos y basicamente lo que se hace con el flashMap es crear otro stream(), obteniendo de esta forma
la union de los objetos que se tienen en una sola lista:

![Image text](https://github.com/andres4715-gif/importanDocuments/blob/master/imagenes/flatMap.png)

- Example 1 con Integer:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class DemoFlatMap {

    public static void main(String[] args) {

        // Adding data into the objects:
        List<Integer> myNewObject1 = Arrays.asList(1, 2);
        List<Integer> myNewObject2 = Arrays.asList(3, 4);
        List<Integer> myNewObject3 = Arrays.asList(5, 6);

        List<List<Integer>> mainTotalList =
                Arrays.asList(myNewObject1, myNewObject2, myNewObject3); // ya se tienen varios array como objetos.

        List<Integer> finalResult = mainTotalList
                .stream()
                .flatMap(x -> x.stream())
                .map(z -> z + 10) // aplica solo si es necesario hacer alguna modificación a los datos.
                .collect(Collectors.toList());
        System.out.println(finalResult);
    }
}

- El output es:

[11, 12, 13, 14, 15, 16]
```

- Example 2 con String:

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class DemoFlatMap {

    public static void main(String[] args) {

        // Adding data into the objects:
        List<Integer> myNewObject1 = Arrays.asList(1, 2);
        List<Integer> myNewObject2 = Arrays.asList(3, 4);
        List<Integer> myNewObject3 = Arrays.asList(5, 6);

        List<List<Integer>> mainTotalList =
                Arrays.asList(myNewObject1, myNewObject2, myNewObject3); // ya se tienen varios array como objetos.

        List<Integer> finalResult = mainTotalList
                .stream()
                .flatMap(x -> x.stream())
                .collect(Collectors.toList());
        System.out.println(finalResult);
    }
}

- El output es:

[Andres, Carmen, Esteban, Juan, Camilo, laura, Iroman, Thor, Spiderman]
```

- Example 3 trabajando con objetos y obteniendo una lista de datos especificos de la lista:

```java

- Dada la lista de Student con su respectivo constructor, de esta forma:

public class Student {

    String name;
    int id;
    char grade;

    Student(String name, int id, char grade) {
        this.name = name;
        this.id = id;
        this.grade = grade;
    }
}

- Es posible trabajar de esta forma:

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class DemoFlatMap3 {

    public static void main(String[] args) {

        List<Student> myStudentList = new ArrayList<>();
        myStudentList.add(new Student("Andres", 89, '9'));
        myStudentList.add(new Student("Liliana", 887, '7'));
        myStudentList.add(new Student("Katherine", 98765, '5'));

        List<Student> myStudentList2 = new ArrayList<>();
        myStudentList2.add(new Student("Camilo", 6543, 'A'));
        myStudentList2.add(new Student("Carmen", 7654, 'B'));
        myStudentList2.add(new Student("Stevan", 998, 'C'));

        List<List<Student>> studentList = Arrays.asList(myStudentList, myStudentList2);

        List<String> finalResultStudentList = studentList
                .stream()
                .flatMap(x -> x.stream())
                .map(z -> z.name)
                .collect(Collectors.toList());
        System.out.println(finalResultStudentList);
    }
}

- El output es:

[Andres, Liliana, Katherine, Camilo, Carmen, Stevan]
```
