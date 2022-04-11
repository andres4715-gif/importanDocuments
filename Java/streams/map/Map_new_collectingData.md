# _MAP Example_

- Ejemplo de MAP:

- Teniendo en cuenta la lista:

```java
import java.util.Arrays;
import java.util.List;

public class StringListToPracticeMap {

    public static List<String> stringList() {
        List<String> MyListObject = Arrays.asList(
                "bus", "car", "bycycle", "flight", "Train");
        return MyListObject;
    }
}
```

- Se va a trabajar con el Map para optener la lista de forma organizada y su contenido en MAYUSCULAS

```java
import java.util.List;
import java.util.stream.Collectors;

public class MainStringListToPracticeMap {

    public static void main(String[] args) {
        List<String> myNewList = StringListToPracticeMap.stringList();

        List<String> checkNewList = myNewList.stream()
                .map(x -> x.toUpperCase())
                .sorted()
                .distinct()
                .collect(Collectors.toList());
        System.out.println(checkNewList);
    }
}
```

El output es:

```shell
[BUS, BYCYCLE, CAR, FLIGHT, TRAIN]
```
