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
    }
}
```

Dada la clase main:

```java
public class Ejercicio1 extends Data {

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

# Tambien se puede trabajar creando un instancia (Objeto) de la clase

Para hacer esto, lo vamos a trabajar de la siguiente forma:

1. Los metodos de la clase a heredar no tienen que se estaticos.

```java
public class Data {

    public void sumaAndmedia(int[] A) {
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
}
```

2. Es necesario crear un objeto de la clase y no es necesaro extender de la clase ya que los metodos no son staticos.

```java
public class Ejercicio1 {

    public static void main(String[] args) {
        Data hs = new Data();
        hs.sumaAndmedia(new int[]{1, 2, 3, 4, 5, -1, -2, -3, -4, -5});
    }
}
```

---

# Tambien se puede trabajar sin necesidad de crear un objeto o extendiendo de la clase:

Esto se logra simplemente con un metodo statico en la clase donde esta el metodo con el cual vamos a trabajar

1. Se agrega la palabra estatic en el metodo que se quiere ver en la otra clase:

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
    }
```

2. En la clase donde heredamos se agrega este metodo statico en los imports:

```java
import static ejerciciosJava.practicando.arrays.Data.sumaAndmedia;
```

3. Se trabaja con el metodo deseado sin necesidad de crear objetos o extender la clase:

```java
import static ejerciciosJava.practicando.arrays.Data.sumaAndmedia;

public class Ejercicio1 {

    public static void main(String[] args) {
        sumaAndmedia(new int[]{1, 2, 3, 4, 5, -1, -2, -3, -4, -5});
    }
}
```
