# **Tomar el numero minimo de una lista**

Para este ejemplo se tienen los datos en un array y lo que se hace es pasar el array a una lista de enteros y luego con la clase Collections.min se toma el valor minimo de la nueva lista de numeros:

Ejemplo:

```java
public class Listas {
    public static void main(String[] args) {
        Integer[] hola = {34, 54, 56, 67};

        List<Integer> myIntegerList = Arrays.asList(hola);
        int numeroMasGrande = Collections.min(myIntegerList);
        System.out.println(numeroMasGrande);
    }
}

Output:
34
```
