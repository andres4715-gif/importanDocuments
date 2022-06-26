# _Trabajando con Hashset_

HashSet contiene un conjunto de objetos, pero de una manera que le permite determinar fácil y rápidamente si un objeto ya está en el conjunto o no. Lo hace administrando internamente una matriz y almacenando el objeto utilizando un índice que se calcula a partir del código hash del objeto.

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

public class DemoTask1 {

    public static void main(String[] args) {
        DemoTask1 mi = new DemoTask1();
        System.out.println(mi.solution(new int[]{1,3,6,4,1,2}));
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
