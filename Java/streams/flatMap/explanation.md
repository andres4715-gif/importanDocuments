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

- Example 1:

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
```

- El output es:

```java
[11, 12, 13, 14, 15, 16]
```
