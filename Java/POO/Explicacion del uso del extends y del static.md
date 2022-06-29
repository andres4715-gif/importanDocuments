# Extends, static y su uso con ejemplo real:

Vamos a mirar como es el tema del uso del extends y la forma correcta del static.

Dado estas dos clases:

```java
public class Data {

    public static void sumaAndmedia(int[] A) {
        double sumaPos = 0;
        double sumaNeg = 0;
        int pos = 0;
        int neg = 0;

        for (int i = 0; i < A.length; i++) {
            if (A[i] >= 0) {
                sumaPos += A[i];
                pos++;
            } else {
                sumaNeg += A[i];
                neg++;
            }
        }

        System.out.println("Positivos son: " + sumaPos);
        System.out.println("Negativos son: " + sumaNeg);
        System.out.println("Cantidad positivos son: " + pos);
        System.out.println("Cantidad negativos son: " + neg);

        System.out.println("Media positivos es: " + (sumaPos / pos));
        System.out.println("media negativos es: " + (sumaNeg / neg));
    }
}
```

Data la clase main:

```java
public class Ejercicio1 extends Data {

    /*
     * Programa que lea por teclado 10 números enteros y los guarde en un array.
     * A continuación calcula y muestra la media de los valores positivos y la  de los valores negativos.
     */

    public static void main(String[] args) {
        sumaAndmedia(new int[]{1, 2, 3, 4, 5, -1, -2, -3, -4, -5});
    }
}
```

Explicación del uso del extends:

- Cuando una clase hereda de otra y se requiere utilizar todos los metodos de la clase la cual estamos heredando tiene que cumplir algunas condiciones:

1. La clase que vamos a heredar tiene que ser statica

```java
    public static void sumaAndmedia(int[] A) {
        double sumaPos = 0;
        double sumaNeg = 0;
        int pos = 0;
        int neg = 0;

        for (int i = 0; i < A.length; i++) {
            if (A[i] >= 0) {
                sumaPos += A[i];
                pos++;
            } else {
                sumaNeg += A[i];
                neg++;
            }
        }
    }

```

2. En la clase donde vamos a heredar se debe agregar despues del nombre de la clase la palabra extends

```java
public class Ejercicio1 extends Data {

    public static void main(String[] args) {
        sumaAndmedia(new int[]{1, 2, 3, 4, 5, -1, -2, -3, -4, -5});
    }
}

```

De esta forma es posible ver los metodos de la clase que se quiere trabajar en este caso no es necesario crear objetos de la clase.

---

# Tambien se puede trabajar creando un intancia (Objeto) de la clase

Para hacer esto, lo vamos a trabajar de la siguiente forma:
