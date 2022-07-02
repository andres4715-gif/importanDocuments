# **Saber Que Cantidad De Datos Tiene**

Para saber la cantidad de datos del HashMap solo es usar la clase size(); de la siguiente forma

## NOTA:

Con el HashMap se tiene que tener en cuenta que no se toman datos si tienen la misma llave, por ese motivo solo toma 4 datos

```java
import java.util.HashMap;

public class SaberQueCantidadDeDatosTiene {

    public static void main(String[] args) {
        HashMap<String, Integer> calzado = new HashMap<>();
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);
        calzado.put("Liliana", 36);
        calzado.put("Daniel", 41);
        calzado.put("Andres", 40);
        calzado.put("Katherine", 37);

        int cantidadDatos = calzado.size();
        System.out.println(cantidadDatos);
    }
}

Output:
4
```
