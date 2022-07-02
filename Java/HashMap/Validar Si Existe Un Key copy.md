# **Validar si existe un key**

La clase constainsKey retorna un valor boolean:

Example:

```java
import java.util.HashMap;

public class ValidarSiExisteUnKey {

    static String data = "Andres";

    public static void main(String[] args) {
        HashMap<String, Integer> calzado = new HashMap<>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        boolean checkingData = ValidarSiExisteUnKey.checKey(calzado);
        System.out.println(checkingData);
    }

    private static boolean checKey(HashMap dataCalzada) {
        boolean checkValue = dataCalzada.containsKey(data);
        return checkValue;
    }
}

Output:
true
```
