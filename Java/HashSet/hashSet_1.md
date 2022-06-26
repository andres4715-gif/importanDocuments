# _Trabajando con Hashset_

HashSet contiene un conjunto de objetos, pero de una manera que le permite determinar fácil y rápidamente si un objeto ya está en el conjunto o no. Lo hace administrando internamente una matriz y almacenando el objeto utilizando un índice que se calcula a partir del código hash del objeto.

Una de las funciones principales de hashset es organizar los datos como ejemplo se puede tomar datos tipo String o Integer de la siguiente forma:

Ejemplo ordenando un array de strings:

```java

import java.util.HashSet;

public class hashsetEjercicio1 {

    public static void main(String[] args) {

        // create a hashset
        HashSet hs = new HashSet();
        hs.add("B");
        hs.add("A");
        hs.add("D");
        hs.add("E");
        hs.add("C");
        hs.add("F");
        System.out.println(hs);
    }
}

Output:
[A, B, C, D, E, F]
```

Ejemplo ordenando un array de integers:

```java
import java.util.HashSet;

public class hashsetEjercicio1 {

    public static void main(String[] args) {

        // create a hashset
        HashSet hs = new HashSet();
        hs.add(3);
        hs.add(7);
        hs.add(87);
        hs.add(1);

        System.out.println(hs);
    }
}

Output:
[1, 3, 7, 87]
```

Otra de las funciones de hashMap es fuera de organizar los arrays segun su orden natural es remover los duplicado:

Ejemplo:

```java
import java.util.HashSet;

public class hashsetEjercicio1 {

    public static void main(String[] args) {

        // create a hashset
        HashSet hs = new HashSet();
        hs.add(3);
        hs.add(3);
        hs.add(87);
        hs.add(1);
        hs.add(3);
        hs.add(3);
        hs.add(87);
        hs.add(1);

        System.out.println(hs);
    }
}
Output:
[1, 3, 87]
```

Ejercicio:

Escribe la funcion:

```java
    class Solution {
        public int solution(int[] A);
    }
```

Dato que el array A tiene N cantidad de enteros, retornar el numero entero positivo que no esta en el array,

Ejemplos:

Dado A = [1,3,6,4,1,2] la funcion debe retormar 5

Dado A = [1,2,3] la funcion debe retornar 4

Dado A = [-1, -3] la funcion debe retornar 1

Solución:

```java
import java.util.HashSet;

public class Solucion {

    public static int[] A = {1, 3, 6, 4, 1, 2};

    public static void main(String[] args) {
        Solucion mi = new Solucion();
        System.out.println(mi.solution(A));
    }

    public int solution(int[] A) {
        HashSet<Integer> nums = new HashSet<Integer>();

        for (int i = 1; i <= A.length + 1; i++) {
            nums.add(i);
        }

        for (int a : A) {
            nums.remove(new Integer(a));
        }
        return nums.iterator().next();
    }
}

output:
5
```
