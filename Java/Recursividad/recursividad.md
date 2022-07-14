# Recursividad.

En Java los métodos pueden llamarse a sí mismos. Si dentro de un método existe la llamada a sí mismo decimos que el método es recursivo.

Ejemplos:

```java
public class Ejercicio1 {

    public static void main(String[] args) {
        hola(1);
    }

    public static void hola(int contador) {
        if(contador <= 5) {
            System.out.print(contador + " ");
            hola(contador + 1);
        }
    }
}

Output:
1 2 3 4 5
```
