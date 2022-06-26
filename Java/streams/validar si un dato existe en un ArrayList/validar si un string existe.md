## _Validar si un dato tipo string existe en un array list_

Buscar elemento con contains

Si queremos saber simplemente si un elemento existe dentro de un ArrayList invocamos a contains que devuelve un booleano.

Example:

```java
import java.util.ArrayList;

class Main {
	public static void main(String[] args) {

		ArrayList<String> canciones = new ArrayList<>();
		// Le agregamos datos
		canciones.add("Beds are burning");
		canciones.add("It's only rock 'n' Roll (But I like it)");
		canciones.add("Ashes to ashes");

		String busqueda = "Ashes to ashes";
		boolean existe = canciones.contains(busqueda);
		if (existe) {
			System.out.println("El elemento SÍ existe en la lista");
		} else {
			System.out.println("El elemento no existe");
		}
	}
}
```

Buscar elemento con indexOf

Este método devuelve -1 o el índice que el elemento ocupa dentro del ArrayList. Funciona para saber si el elemento existe dentro del ArrayList y para saber cuál índice tiene al mismo tiempo.

Su uso es el siguiente:

```java

import java.util.ArrayList;

class Main {
	public static void main(String[] args) {

		ArrayList<String> canciones = new ArrayList<>();
		// Le agregamos datos
		canciones.add("Beds are burning");
		canciones.add("It's only rock 'n' Roll (But I like it)");
		canciones.add("Ashes to ashes");

		String busqueda = "Ashes to ashes";
		int indice = canciones.indexOf(busqueda);
		if (indice != -1) {
			System.out.println("La búsqueda está en el índice " + indice);
		} else {
			System.out.println("El elemento no existe");
		}
	}
}
´´´

```
