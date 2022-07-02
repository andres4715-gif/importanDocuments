# **Añadir un elemento a un HashMap**

Para agregar datos a un HashMap se debe agregar el metodo put de la siguiente forma:

```java
import java.util.HashMap;

public class AddNewElement {

    public static void main(String[] args) {
        HashMap<String, Integer> calzado = new HashMap<String, Integer>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);

        System.out.println(calzado);
    }
}

Output:
{Andres=40, Liliana=36, Daniel=41}
```
