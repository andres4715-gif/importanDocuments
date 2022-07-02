# **Obtener Los Valores De Cada Elemeto**

```java
import java.util.HashMap;

public class ObtenerLosValoresDeCadaElemeto {

    public static void main(String[] args) {

        HashMap<String, Integer> calzado = new HashMap<>();

        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        for(int tallaCalzado : calzado.values()) {
            System.out.println(tallaCalzado);
        }
    }
}

Output:
40
36
37
41
```

Para el manejo de estos valores hay que tener en cuenta que con lo que se esta trabajadon son Arrays y se debe tratar como tal

Ejemplo:

```java
import java.util.HashMap;

public class ObtenerLosValoresDeCadaElemeto {

    public static void main(String[] args) {

        HashMap<String, Integer> calzado = new HashMap<>();
        int sumaCalzado = 0;

        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        for (int tallaCalzado : calzado.values()) {
            sumaCalzado = sumaCalzado + tallaCalzado;
        }
        System.out.println("la suma de todo el calzado es: " + sumaCalzado);
    }
}

OUTPUT:
la suma de todo el calzado es: 154
```

---

Ejemplo con las KEY

```java
public class ObtenerLosValoresDeCadaElemeto {

    public static void main(String[] args) {

        HashMap<String, Integer> calzado = new HashMap<>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        int contador = 1;
        for (String nombres : calzado.keySet()) {
            System.out.println(nombres + contador);
            contador ++;
        }
    }
}

Output.
Andres1
Liliana2
Katherine3
Daniel4
```
