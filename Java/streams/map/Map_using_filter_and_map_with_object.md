# _Example using Map and Filter with object_

- Dada la clase:

```java
import lombok.AllArgsConstructor;
import lombok.Data;

@Data
@AllArgsConstructor
public class Persona {
    private String name;
    private String lastName;
    private int age;
}
```

- Se va a realizar un filtro y despues el map para obtener los mayores de 18 de un objeto

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class MainPersona {
    public static void main(String[] args) {
        List<Persona> personaList = Arrays.asList(
                new Persona("Andres", "Rios", 34),
                new Persona("Liliana", "Rios", 20),
                new Persona("Daniel", "Rios", 17),
                new Persona("Katerine", "Avila", 12),
                new Persona("Andres", "Rios", 34)
        );

        List<String> checkingPersona = personaList
                .stream()
                .filter(p -> p.getAge() > 18)
                .map(x -> x.getName())
                .distinct()
                .collect(Collectors.toList());
        System.out.println(checkingPersona);
    }
}
```

- El output es:
  [Andres, Liliana]
