# _Convertir una Array de Integer a una lista y crear un nuevo array con los datos que cumplan una condición:_

Ejemplo:

- En este ejercicio nos dan un array de enteros y es necesario sacar los numeros enteros del array y crear otro con esos datos.

Una opción valida para hacer esto es pasar ese array a una lista y ya como ese tipo de dato ya es posible añadir datos que cumplan alguna condición

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

/*
        desde un array con 10 numeros crear un array nuevo con los numeros pares
 */
public class Ejercicio4 {

    public static void main(String[] args) {

        int[] arrayDeNumeros = {10, 20, 30, 40, 50, 41, 43, 57, 89, 97};
        List<Integer> nuevaLista = new ArrayList<>();
        List<Integer> list = Arrays.stream(arrayDeNumeros).boxed().collect(Collectors.toList());

        for(int numero : list) {
            if(numero % 2 == 0) {
                nuevaLista.add(numero);
            }
        }
        System.out.println(nuevaLista);
    }
}

Output:

[10, 20, 30, 40, 50]
```
