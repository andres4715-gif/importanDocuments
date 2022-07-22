# Agregar nuevos elementos a una array en Java

Para mas información consultar esta [pagina](<https://www.techiedelight.com/es/add-new-elements-to-array-java/#:~:text=arraycopy()%20m%C3%A9todo,de%20la%20array%20de%20destino.>)

Sabemos que el tamaño de una arrays no se puede modificar una vez que se crea. No hay forma de cambiar el tamaño de las arrays de tamaño fijo en Java para acomodar elementos adicionales.

Si necesitamos una estructura de datos basada en array dinámicas, la solución recomendada es utilizar un ArrayList. Un ArrayList es una implementación de array redimensionable de la List interfaz. Esta clase proporciona métodos para manipular fácilmente el tamaño de la array. A medida que se agregan elementos al ArrayList, su capacidad crece automáticamente. La capacidad es el tamaño de la array utilizada para almacenar los elementos de la lista.

```java
import java.util.ArrayList;

public class Ejercicio7 {

    // crear un nuevo array partiendo de los datos de otro cumpliendo una condición

    public static void main(String[] args) {
        ArrayList myList = addingDataToTheArrayList(new int[]{11, 21, 31, 41, 51, 61, 71, 80, 90, 100});
        System.out.println(myList);
    }

    public static ArrayList addingDataToTheArrayList(int[] myData) {
        ArrayList<Integer> adding = new ArrayList<Integer>();
        for (int i = 0; i < myData.length; i++) {
            if (myData[i] > 50) {
                adding.add(myData[i]);
            }
        }
        return adding;
    }
}

Output:
[51, 61, 71, 80, 90, 100]
```

Pero si insiste en usar arrays, debe crear una instancia de una nueva arrays para acomodar el elemento adicional. Esto lo podemos hacer con cualquiera de los siguientes métodos:

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class Ejercicio8 {

    public static void main(String[] args) {
        Integer[] nums = {1, 2, 3, 4};

        nums = myData(nums, 5);    // suma 5 a `nums[]`
        System.out.println(Arrays.toString(nums));
    }

    private static Integer[] myData(Integer[] arr, int element) {
        List<Integer> list = new ArrayList<>(Arrays.asList(arr));
        list.add(element);

        return list.toArray(new Integer[0]);
    }
}

OUTPUT:
[1, 2, 3, 4, 5]
```
