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

---

Otro ejemplo:

```java
public class Ejercicio8 {

    /*
         Dado como datos las calificaciones de 15 alumnos de la materia de fundamentos de programación,
         realiza un programa en JAVA que obtenga lo siguiente:
-        Promedio general
-        Imprima las calificaciones en orden inverso
    */

    public static void main(String[] args) {
        double calificaciones[] = {4.0, 2.0, 3.0, 4.3, 5.7, 5.9, 7.1, 2.8, 6.8, 9.0, 7.8, 8.9, 9.8, 7.7, 8};
        double suma = 0;
        double media = 0;
        int cantidadNotas = calificaciones.length;

        for (double data : calificaciones) {
            suma += data;
            media = (suma / cantidadNotas);
        }

        for (int i = calificaciones.length -1; i >= 0; i--) {
            System.out.println(calificaciones[i]);
        }
        System.out.println("La media de todos los alumnos es: " + media);
    }
}

Output:

8.0
7.7
9.8
8.9
7.8
9.0
6.8
2.8
7.1
5.9
5.7
4.3
3.0
2.0
4.0
La media de todos los alumnos es: 6.1866666666666665
```
