## _Validar si un dato tipo Integer existe en un array list_

Esto se puede hacer de varias formas:

1. Usando List.contains() método

Para verificar si una Lista contiene un elemento dado o no, simplemente puede usar el List.contains() método como se demuestra a continuación:

```java
import java.util.Arrays;
import java.util.List;

class Main
{
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);
        int value = 3;

        boolean isExists = list.contains(value);
        System.out.println(isExists);
    }
}

output:
true
```
