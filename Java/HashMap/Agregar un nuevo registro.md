# **Agregar un nuevo registro:**

Ejemplo:

```java
import java.util.HashMap;

public class AgregarUnNuevoRegistro {

    public static void main(String[] args) {

        HashMap<String, Integer> calzado = new HashMap<>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        addAllHashMap(calzado, "Rosalba", 36);
        System.out.println("la nuevo lista despues del metodo es: ");
        for (String print : calzado.keySet()) {
            System.out.println(print);
        }
    }

    public static void addAllHashMap(HashMap<String, Integer> mio, String key, Integer value) {
        mio.put(key, value);
        System.out.println("La llave ingresada es: " + key);
    }
}

Output:
Andres
Liliana
Katherine
Daniel
Rosalba
```
