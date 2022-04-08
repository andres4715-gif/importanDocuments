# _Filter example:_

## Obteniendo de una lista de Integer con el metodo filter creando una nueva lista:

## _Data la clase con la lista:_

```java
import java.util.ArrayList;

public class Datum {

    public static ArrayList<Integer> myInteger_arrayList() {
        ArrayList<Integer> numberList = new ArrayList<>();
        numberList.add(10);
        numberList.add(15);
        numberList.add(20);
        numberList.add(25);
        numberList.add(30);
        return numberList;
    }
}
```

- Aplicando el metodo filter:

```java
import java.util.List;
import java.util.stream.Collectors;

public class FilterDemo1 {
    public static void main(String[] args) {
        List<Integer> newIntegerList;
        List<Integer> myDataIntegerList = Datum.myInteger_arrayList();

        newIntegerList = myDataIntegerList
                .stream()
                .filter(x -> x % 2 == 0)
                .sorted()
                .collect(Collectors.toList());
        System.out.println(newIntegerList);
    }
}
```

Output:
[10, 20, 30]
