# **Tomar el numero maximo de una lista**

Para este ejemplo se tienen los datos en un array y lo que se hace es pasar el array a una lista de enteros y luego con la clase Collections.max se toma el valor mas grande de la nueva lista de numeros:

Ejemplo:

```java
public class Listas {
    public static void main(String[] args) {
        Integer[] hola = {34, 54, 56, 67};

        List<Integer> myIntegerList = Arrays.asList(hola);
        int numeroMasGrande = Collections.max(myIntegerList);
        System.out.println(numeroMasGrande);
    }
}

Output:
67
```
