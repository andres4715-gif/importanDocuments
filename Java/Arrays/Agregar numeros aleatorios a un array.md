# Agregar numeros aleatorios a un array

Se debe utilizar el metodo: Math.random()

```java
public class Ejercicio10 {

    public static void main(String[] args) {

        ArrayList<Integer> myData = new ArrayList<Integer>();

        for (int i = 0; i < 10; i++) {
            int aleatorio = (int) ((Math.random() * 10) + 1);
            myData.add(aleatorio);
        }
        System.out.println(myData);
    }
}

Output:
[6, 9, 5, 1, 5, 2, 6, 6, 5, 9]
```
