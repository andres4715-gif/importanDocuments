# **Validar si existe un key**

La clase constainsKey retorna un valor boolean:

Example:

```java
import java.util.HashMap;

public class ValidarSiExisteUnValor {

    public static void main(String[] args) {

        HashMap<String, Integer> calzado = new HashMap<>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        boolean checkValue = calzado.containsValue(40);
        System.out.println(checkValue);
    }
}

Output:
true
```
