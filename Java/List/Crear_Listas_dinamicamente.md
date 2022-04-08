# _List_

- Para crear una lista dinamicamente, se puede hacer de la siguiente forma:

```java
* Ejemplo1:

import java.util.Arrays;
import java.util.List;


List<Integer> myIntegerList = Arrays.asList(10, 12, 20, 45, 45, 54);
List<String> myStringList = Arrays.asList("Andrse", "Carlos", "Liliana", "Stevan");
List<Boolean> myBooleanList = Arrays.asList(true, false);
```

```java
* Ejemplo2:

import java.util.Arrays;
import java.util.List;


Integer[] hola = {34, 54, 56, 67};

    List<Integer> words = Arrays.asList(hola);
        System.out.println(words);

// output
[34, 54, 56, 67]
```

```java
* Ejemplo3:

import java.util.stream.Collectors;

    int[] myArray = {2, 12, 34, 56, 1, 76, 87, 29, 676, 76, 7,};

    ArrayList<Integer> nyList = (ArrayList<Integer>) Arrays.stream(myArray)
    .boxed()
    .collect(Collectors.toList());
        System.out.println(nyList);

// output
[2, 12, 34, 56, 1, 76, 87, 29, 676, 76, 7]
```
