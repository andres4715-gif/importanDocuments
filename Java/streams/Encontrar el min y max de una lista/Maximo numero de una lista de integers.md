# _Para encontrar el numero mas grande de una lista se hace lo siguiente:_

NOTA: Este ejemplo se hizo tomando un array y lo convertimos en una lista de integers

Ejemplo:

```java
 int[] A = {1, 3, 6, 4, 1, 2};
        List<Integer> list = Arrays.stream(A).boxed().collect(Collectors.toList());

        Integer maxValue = list.stream()
                .max(Comparator.naturalOrder())
                .get();
        System.out.println(maxValue);

output:
6
```
