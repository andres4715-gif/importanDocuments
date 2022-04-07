## Metodo MAP (param : function)

- Este permite modificar los elementos que se esten trabajando en el stream.

- Lo que se espera que retorne el mapa es un parametro o un valor producto del resultado de la funcion que se haya hecho.

```shell

Puede aplcar para estos casos pero son muchos mas:

1. Transformar un tipo de dato a otro tipo de dato.
2. Aplicar alguna concatenación de variables.
3. Hacer alguna logica como (Multiplicación, Suma etc...).

Para este caso tenemos una lista y de esta se quire obtener una lista
con las marcas de los relojes que tengan un precio mayor a 300.

Nota: Recordar que el .collect() se debe hacer sobre la ultima linea antes de agregar el .collect().

Eso quiere decir que es posible hacer la n cantidad de filtros o modificaciones antes de llegar a un estado final.

Teniendo el siguiente modelo.

import lombok.Getter;
import lombok.Setter;

@Getter
@Setter
public class Model {

    // constructor
    public Model(String marca, String modelo, boolean disponibilidad, double precio, double importacion) {
        this.marca = marca;
        this.modelo = modelo;
        this.disponibilidad = disponibilidad;
        this.precio = precio;
        this.importacion = importacion;
    }

    private String marca;
    private String modelo;
    private boolean disponibilidad;
    private double precio;
    private final double IVA = 19;
    private double importacion;

    }
}


Y despues de crear nuevos objetos de la clase (Model) de esta forma:

        List<Model> myList = new ArrayList<>();

        myList.add(new Model("Samsung", "Galaxy", true, 200, 10));
        myList.add(new Model("Huawei", "HRT12", false, 300, 10));
        myList.add(new Model("Poco", "Poco56P", true, 400, 10));
        myList.add(new Model("HTC", "HCH78H", false, 500, 10));

Se quiere obtener los nombres de los reloges que superan el costo es mayor de 300

La respuesta que debemos obtener despues de hacer el .collet() es:

Poco
HTC

Vamos al codigo:

private static void relogesMasCaros(List<Model> ownList, double totalValue) {
        List<String> mio = ownList
                .stream()
                .filter(x -> x.getPrecio() > 300)
                .map(x -> x.getMarca())
                .collect(Collectors.toList());
        MainSmartWatch.printList(mio);
    }

    public static void printList(List<?> list) {
        list.forEach(System.out::println);
    }

Esto retorna una respuesta por consola de una lista con los nombre de los reloges que el costo es mayor de 300

Poco
HTC
```
