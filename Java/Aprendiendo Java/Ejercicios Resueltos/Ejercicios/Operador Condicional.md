# Java Ejercicios iniciales 3. Operador Condicional ? :

[Click](http://puntocomnoesunlenguaje.blogspot.com/2012/10/java-ejercicios-iniciales-3.html) para mas información

- En esta entrada vamos a ver tres ejemplos de utilización del operador condicional ? :

Se trata de usar el operador condicional en lugar de la instrucción condicional if para mostrar por pantalla un mensaje u otro dependiendo de una condición.

```text
Ejercicio básico inicial 5

Escribe un programa java que declare una variable A de tipo entero y asígnale un valor. A continuación muestra un mensaje indicando si A es par o impar. Utiliza el operador condicional ( ? : ) dentro del println para resolverlo.
Si por ejemplo A = 14 la salida será
14 es par
Si fuese por ejemplo A = 15 la salida será:
15 es impar
```

```java
package ejerciciosJava;

public class OperadorCondicional {
    public static void main(String[] args) {

        int A = 10;
/*        if (A % 2 == 0) {
            System.out.println("El numero es par");
        } else {
            System.out.println("El numero es impar");
        }*/

        System.out.println(A + (A % 2 == 0 ? " Es entero" : " No es entero"));
    }
}

```

## output

10 Es entero
