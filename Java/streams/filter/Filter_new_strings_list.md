# _Filter example:_

## Obteniendo de una lista de String con el metodo filter creando una nueva lista:

## _Data la clase con la lista:_

```java
import java.util.ArrayList;
import java.util.List;

public class DatumString {

    public static List<String> theNameList() {
    List<String> names = new ArrayList<>();
        names.add("Omar");
        names.add("Andres");
        names.add("Liliana");
        names.add("Carmen");
        names.add("Stevan");
        names.add("Rosalba");
        names.add("Luz");
        return names;
    }
}
```

- Aplicando el metodo filter:

```java
import java.util.List;
import java.util.stream.Collectors;

public class FilterDemoString1 {

    public static void main(String[] args) {
        List<String> myDataString = DatumString.theNameList();
        List<String> shortNames;

        shortNames = myDataString
                .stream()
                .filter(str -> str.length() >= 3 && str.length() <= 6)
                .sorted()
                .collect(Collectors.toList());

        System.out.println(shortNames);
    }
}
```

- Output:
  [Andres, Carmen, Luz, Omar, Stevan]
