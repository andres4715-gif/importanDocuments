# _Filter removing null values example:_

## Obteniendo de una lista de String con Null values, con el metodo filter creando una nueva lista:

## _Data la clase con la lista:_

```java
import java.util.Arrays;
import java.util.List;

public class DataValues {

    public static List<String> myStringDataList() {
        List<String> saludos_and_despedidas = Arrays.asList("hola", "hi", "Hello", null, "Chiao", null, "chao");
        return saludos_and_despedidas;
    }
}
```

- Aplicando el metodo filter:

```java
import java.util.List;
import java.util.stream.Collectors;

public class UsingDataList {

    public static void main(String[] args) {
        List<String> checking_saludos_and_despedidas = DataValues.myStringDataList();
        List<String> removingNullsValues;

        removingNullsValues = checking_saludos_and_despedidas
                .stream()
                .filter(x -> x != null)
                .collect(Collectors.toList());
        System.out.println(removingNullsValues);
    }
}
```

- Output:
  [hola, hi, Hello, Chiao, chao]
