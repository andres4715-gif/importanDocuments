## _STREAMS_

- Lo primero que se debe saber de los .streams es que utilizan lambdas para su funcionamiento y a partir de ahi se puede lograr trabajar con colecciones de datos aplicando diferentes metodos como

.filter()

.sorted()

.map() ...

- La documentación se puede ver en esta [Pagina](https://www.youtube.com/watch?v=U5oOdNG2XQY)

## Dada la clase personas:

```shell
package javaPractice.stream.entendiendoStreams;

import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

import java.time.LocalDate;

@Data
@AllArgsConstructor
@NoArgsConstructor
public class Person {
    private int id;
    private String name;
    private LocalDate birthday;
}
```

## Dada la clase Productos:

```shell
package javaPractice.stream.entendiendoStreams;


import lombok.AllArgsConstructor;
import lombok.Data;
import lombok.NoArgsConstructor;

@Data
@AllArgsConstructor
@NoArgsConstructor
public class Product {
    private int id;
    private String name;
    private double price;
}
```

## Dada la clase main() con los objetos de las clases person y product creados

```shell
package javaPractice.stream.entendiendoStreams;

import java.time.LocalDate;
import java.time.Period;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

// Esto esta en el proyecto
// selenium_4
// En la ruta: src/main/java/javaPractice/stream/entendiendoStreams

public class App {

    public static void main(String[] args) {

        Person p1 = new Person(1, "Andres", LocalDate.of(2003, 1, 21));
        Person p2 = new Person(2, "Jorge", LocalDate.of(2000, 3, 23));
        Person p3 = new Person(3, "Estevan", LocalDate.of(1960, 2, 11));
        Person p4 = new Person(4, "Liliana", LocalDate.of(1979, 4, 3));
        Person p5 = new Person(5, "Camilo", LocalDate.of(1980, 5, 22));

        Product prod1 = new Product(1, "ceviche", 34.6);
        Product prod2 = new Product(2, "galleta", 34.6);
        Product prod3 = new Product(3, "chocolatina", 34.6);
        Product prod4 = new Product(4, "mandarina", 34.6);

        List<Person> persons = Arrays.asList(p1, p2, p3, p4, p5);
        List<Product> products = Arrays.asList(prod1, prod2, prod3, prod4);

```

## Es posible iniciar a jugar con las listas o colecciones con los diferentes metodos

### Se puede imprimir la lista con un metodo forEach tradicional de esta forma:

```shell

- Para recorrer las listas con un foreach

        for(Person myDataPerson : persons){
            System.out.println(myDataPerson);
        }

        for(Product myDataProduc : products){
            System.out.println(myDataProduc);
        }

```

### Para ejecutar lo mismo pero con un forEach mas simplificado:

- Esto es lo que se le llama (Expresion Lambda).

```shell
        persons.forEach(person -> System.out.println(person));

        products.forEach(product -> System.out.println(product));

- Pero se puede simplificar mas aún. Java dice que si el paremetro de la izquierda es el mismo que la derecha.

- Se pude declarar de esta forma.

        persons.forEach(System.out::println);
        products.forEach(System.out::println);

```

## Metodo Filter (param : predicate)

- Predicate: Lo que significa es que retorna un booleano (true or false)
  para poder seguir avanzando y obtener la lista que se quiere obtener. claro esta que no es necesario que sea un booleano, solo es un paso que nos permite seguir avanzando a obtener el resultado que queremos para continuar con el flufo que queremos.

```shell

Ejemplo:

        List<Person> filteredList = persons
                .stream()
                .filter(p -> App.getAge(p.getBirthday()) >= 40)
                .collect(Collectors.toList());
        App.printList(filteredList);
    }

    public static int getAge(LocalDate birthDate) {
        return Period.between(birthDate, LocalDate.now()).getYears();
    }

    public static void printList(List<?> list) {
        list.forEach(System.out::println);
    }

- Con el filtro aplicado, se obtiene una nueva lista dondde se cumple la condición.

- En el output se puede ver esto como resultado:

Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=4, name=Liliana, birthday=1979-04-03)
Person(id=5, name=Camilo, birthday=1980-05-22)
```

## Metodo Sorted:

- Teniendo en cuenta la Clase personas, la clase Productos y la Clase App
  donde se tiene las colecciones (Listas). se puede optar por organizar los resultados para que estos queden organizados de la forma que se requiera.

Teniendo en cuenta que se tiene la lista de personas y se quiere tener dicha lista organizada de forma ascendente, esto se puede obtener con la programación funcional de la siguiente forma :

```shell

Lo primero que se debe tener en cuenta es que vamos a requerir una Lista<String>
ya que el dato name es de tipo <String> y vamos a trabajar con la lista (persons) a dicha
colección se el aplica el metodo .stream(), luego el metodo .map() para obtener los nombres,
luego el metodo .sorted() ya en esta parte se tiene la lista de nombres organizada de la forma que queremos.

    List<String> filteredList3 = persons
            .stream()
            .map(p -> p.getName())
            .sorted()
            .collect(Collectors.toList());
        App.printList(filteredList3);

- La lista de nombres real es de esta forma:

Andres
Jorge
Estevan
Liliana
Camilo

- Pero despues de aplicar el metodo .sorted() el resultado por consola que se obtiene es:

Andres
Camilo
Estevan
Jorge
Liliana

______________________________________

- Hacer lo mismo pero con un objeto completo:

- Ahora la necesidad es ordenar no solo los nombres si no que ahora se requiere ordenar por nombre pero
la lista completa, osea el objeto completo

Para poder hacer esto es necesario decirle al metodo .sorted()
por parametro como se quiere organizar el objeto. esto se logra
a traves de un comparator que lo veremos a continuación:

        // sorted(param : comparator)
        // Comparator<persons>

        Comparator<Person> byNameAcs = (Person o1, Person o2) -> o1.getName().compareTo(o2.getName());
        List<Person> filteredList4 = persons
                .stream()
                .sorted(byNameAcs)
                .collect(Collectors.toList());
        App.printList(filteredList4);
    }

        public static void printList(List<?> list) {
        list.forEach(System.out::println);
    }

El output de salida seria de la siguiente forma:

Person(id=1, name=Andres, birthday=2003-01-21)
Person(id=5, name=Camilo, birthday=1980-05-22)
Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=2, name=Jorge, birthday=2000-03-23)
Person(id=4, name=Liliana, birthday=1979-04-03)


- En caso de querer hacerlo de forma descendente solo seria cambiarle el orden al Comparator y el codigo
quedaria de la siguiente forma:

        // Comparator<persons>

        Comparator<Person> byNameDesc = (Person o1, Person o2) -> o2.getName().compareTo(o1.getName());
        List<Person> filteredList4 = persons
                .stream()
                .sorted(byNameDesc)
                .collect(Collectors.toList());
        App.printList(filteredList4);
    }

        public static void printList(List<?> list) {
            list.forEach(System.out::println);
        }
}

El output de salida seria de la siguiente forma:

Person(id=4, name=Liliana, birthday=1979-04-03)
Person(id=2, name=Jorge, birthday=2000-03-23)
Person(id=3, name=Estevan, birthday=1960-02-11)
Person(id=5, name=Camilo, birthday=1980-05-22)
Person(id=1, name=Andres, birthday=2003-01-21)
```

## Match (param : predicate)

- Es una operación de flujo intermedio y se puede utilizar de la siguiente forma:

* anyMatch
* allMatch
* noneMatch

- La operación principal del Match es retornar un booleano (True or False) para poder tomar decisiones con este resultado.

```shell
Ejemplo 1: anyMatch

En este lo que se quiere validar es si dada la lista de personas que tenemos previamente
tenemos por lo menos un dato que inicia con la letra (L) si en la lista se tiene un dato
que inicia con la letra (L) nos va a retornar un true y en caso contrario nos retorna false

- Se puede ver en el ejemplo que no vamos a retornar una lista, solo vamos a retornar un dato boolean.

- Para este especifico, el anyMatch no recorre toda la lista. el simplemente busca que se tenga por lo
menos un dato que cumpla la condición y si encuentra por lo menos un match con eso nos da el true


        boolean rpta1 = persons
                .stream()
                .anyMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta1);

* El output despues de ejecutar va a ser true or false dependiendo si se cumple o no la condición
y con este resultado vamos a podemos seguír avanzando en el programa.

Para este ejemplo la salida fue true

```

```shell
Ejemplo 2: allMatch

- Para el allMatch todos los datos deben coincidir, en este caso tenemos una lista de nombres y esto
implica que al no coinidir la primera letra en todas las iteraciones el va dar como salida un false


        boolean rpta2 = persons
                .stream()
                .allMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta2);

* El output despues de ejecutar va a ser false ya que no se cumple con la condición del allMatch
en todas las iteraciones.
```

```shell
Ejemplo 3: noneMatch

- Para el noneMatch si vamos a trabajar con una lista de personas se debe evaluar cada uno de los
datos que se obtienen de la lista, es este caso vamos a evaluar si alguno de los nombres inicia
con la letra ("L") y como efectivamente hay un dato que es (Liliana) el debe retornar un false


        boolean rpta3 = persons
                .stream()
                .noneMatch(x -> x.getName().startsWith("L"));
        System.out.println(rpta3);

* Cambiando de ejemplo si buscamos con letra ("X") En toda la lista se va a encontrar que no se
tiene nunguna coincidencia y esto hace que el output sea true

        boolean rpta3 = persons
                .stream()
                .noneMatch(x -> x.getName().startsWith("X"));
        System.out.println(rpta3);
```

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
