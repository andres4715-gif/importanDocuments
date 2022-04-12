# _Example using Map and Filter_

- Dada la clase:

```java
import java.util.Arrays;
import java.util.List;

public class IntegerListToPracticeMap {

    public static List<Integer> IntListNewExample() {
        List<Integer> IntegerList
                = Arrays.asList(10, 20, 25, 25, 30, 40);
        return IntegerList;
    }
}
```

- Se va a realizar un filtro de los numeros menores a 10 y el resultado de multiplicara por 3

```java
import java.util.List;
import java.util.stream.Collectors;

public class MainIntegerListToPracticeMap {

    public static void main(String[] args) {
    List<Integer> integerArrayCollection = IntegerListToPracticeMap.IntListNewExample();
        List<Integer> newArrayListResutls = integerArrayCollection
                .stream()
                .filter(x -> x < 20)
                .map(x -> x * 3)
                .sorted() // Para organizarlos
                .distinct() // Para eliminar los repetidos
                .collect(Collectors.toList());
        System.out.println(newArrayListResutls);
    }
}
```
