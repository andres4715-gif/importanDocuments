# _Convertir una Array de Integer a una lista:_

Para hacer esto se puede hacer de varias formas:

Example 0;

Cuando se tiene un array y es necesario convertir ese array en una lista de puede hacer de la siguiente forma:

```java
public class listas {

    public static void main(String[] args) {
        Integer[] hola = {34, 54, 56, 67};

        List<Integer> myIntegerList = Arrays.asList(hola);
        System.out.println("El tipo de dato es: " + myIntegerList.getClass().getSimpleName());
        System.out.println(myIntegerList);
    }
}

Output:
El tipo de dato es: ArrayList
[34, 54, 56, 67]
```

Example 1:

```java
int[] A = {1, 3, 6, 4, 1, 2};
        List<Integer> list = Arrays.stream(A).boxed().collect(Collectors.toList());
        System.out.println(list.get(2));

output:
6
```

Example 2:
Para esta se debe tener en cuenta que el tipo de dato del array es _Integer_

```java
 Integer[] A = {1, 3, 6, 4, 1, 2};

   List<Integer> targetList = new ArrayList<Integer>(Arrays.asList(A));
        System.out.println(targetList.get(5));

output:
2
```
