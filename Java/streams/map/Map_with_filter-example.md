# _USANDO MAP CON FILTER EN LA MISMA COLECCIÓN_

- Example:

- Dada la data en una lista como esta:

```java
import java.util.Arrays;
import java.util.List;

public class StringListToPracticeMap {

    public static List<String> stringList() {
        List<String> MyListObject = Arrays.asList(
                "bus", "car", "bycycle", "flight", "Train","Train");
        return MyListObject;
    }
}
```

- Lo que se quiere hacer es anter de hacer alguna acción es hacer un filtro

```java
import java.util.List;
import java.util.stream.Collectors;

public class DoingFilterAndGettingCollection {

    public static void main(String[] args) {
        List<String> newNamesList;

        List<String> gettingNames = StringListToPracticeMap.stringList();

        newNamesList = gettingNames
                .stream()
                .filter(x -> x.length() > 3)
                .map(x -> x.toUpperCase())
                .sorted()
                .distinct()
                .collect(Collectors.toList());
        System.out.println(newNamesList);
    }
}
```

- El output es:

```shell
[BYCYCLE, FLIGHT, TRAIN]
```
