# Ejercicio para sumar valores en un array y sacar la media:

---

```java
public class Ejercicio1 {

    /*
     * Programa que lea por teclado 10 números enteros y los guarde en un array.
     * A continuación calcula y muestra la media de los valores positivos y la  de los valores negativos.
     */


    public static void main(String[] args) {
        double sumaPos = 0;
        double sumaNeg = 0;
        int pos = 0;
        int neg = 0;

        int[] nums = {1, 2, 3, 4, 5, -1, -2, -3, -4, -5};

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] >= 0) {
                sumaPos += nums[i];
                pos++;
            } else {
                sumaNeg += nums[i];
                neg++;
            }
        }

        System.out.println("La suma de los positivos son: " + sumaPos);
        System.out.println("La suma de los negativos son: " + sumaNeg);
        System.out.println("Los numeros positivos son: " + pos);
        System.out.println("Los numeros negativos son: " + neg);


        System.out.println("la media de los positivos es: " + (sumaPos / pos));
        System.out.println("la media de los negativos es: " + (sumaNeg / neg));
    }
}

Output:
La suma de los positivos son: 15.0
La suma de los negativos son: -15.0
Los numeros positivos son: 5
Los numeros negativos son: 5

la media de los positivos es: 3.0
la media de los negativos es: -3.0
```
