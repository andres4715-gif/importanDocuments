# Accediendo a los elementos del Array usando el bucle for

A cada elemento del array se accede a través de su índice. El índice comienza con 0 y termina en (tamaño total del array) -1. Se puede acceder a todos los elementos de la matriz usando el bucle for en Java.

```java
package ejerciciosJava.practicando.arrays;

public class Checking {
    public static void main(String[] args) {

        int[] intArray = new int[]{12, 26, 38, 4678, 56, 67, 798, 8654, 934, 10344};
        //acceder a los elementos del array
        for (int i = 0; i < intArray.length; i++)
            System.out.println("Elemento en el índice " + i + " : " + intArray[i]);
    }
}

Output:
Elemento en el índice 0 : 12
Elemento en el índice 1 : 26
Elemento en el índice 2 : 38
Elemento en el índice 3 : 4678
Elemento en el índice 4 : 56
Elemento en el índice 5 : 67
Elemento en el índice 6 : 798
Elemento en el índice 7 : 8654
Elemento en el índice 8 : 934
Elemento en el índice 9 : 10344

```

Ejemplo con un forEach:

```java
public class Checking {
    public static void main(String[] args) {
        int[] intArray = new int[]{12, 26, 38, 4678, 56, 67, 798, 8654, 934, 10344};

        int iterador = 1;
        //acceder a los elementos del array
        for (int check : intArray) {
            System.out.println("Elemento en el índice " + iterador + " es:  " + check);
            iterador++;
        }
    }
}
```
