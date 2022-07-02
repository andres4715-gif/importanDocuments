# **Leer un array de derecha a izquierda con un ejemplo:**

---

```java
public class Ejercicio6 {

    /*
        leer un array de atras para adelante
    */

    static int sumaDeDerechaAIzquierda = 0;
    static int sumaDeIzquierdaADerecha = 0;

    public static void main(String[] args) {

        int[] array = {1, 2, 3, 4, 5};

        // Recorrido array derecha izquierda:
        for (int i = array.length - 1; i >= 0; i--) {
            sumaDeDerechaAIzquierda += array[i];
        }

        // Recorrido array izquierda derecha:
        for (int i = 0; i < array.length; i++) {
            sumaDeIzquierdaADerecha += array[i];
        }
        System.out.println("La suma de derecha a izquierda es: " + sumaDeDerechaAIzquierda);
        System.out.println("La suma de izquierda a derecha es: " + sumaDeIzquierdaADerecha);
    }
}

Output:
La suma de derecha a izquierda es: 15
La suma de izquierda a derecha es: 15
```
