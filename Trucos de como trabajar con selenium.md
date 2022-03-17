# _Trucos que se pueden utilizar en la automatizacion_

## Listas

- Como es el manejo de las listas y como es la forma de obtener datos:

```java

- En el page se agrega el elemento que contiene la lista:
- En un metodo que puede retornar <String> se agrega la lista de tipo WebElment.

Ejemplo:

    By crickeet = By.xpath("//*[@id = 'Skills']/option");

    public void checkTheBox() {
        List<WebElement> listOfElements = driver.findElements(crickeet);
        System.out.println(listOfElements.get(1).getText());
    }

- Output:

Esto va a traer el segundo dato de la lista,
en caso de necesitar todos los elememtos de la lista
ya seria con un forEach() que se podria trabajar de la siguiente forma:

    public void checkTheBox() {
        List<WebElement> listOfElements = driver.findElements(crickeet);
        for (WebElement element : listOfElements) {
            System.out.println(element.getText());
        }
    }

Esto traeria todos los elementos de la lista en una colección que se
podria trabajar con los streams().

- Output:

Adobe InDesign
Adobe Photoshop
Analytics
Android
APIs
Art Design
```

## JSON

- Esta es una de las formas que se tiene de trabajar con un archivo tipo JSON
  con formato string:

- En maven se debe importar una Libreria:

```xml
        <!-- https://mvnrepository.com/artifact/org.json/json -->
        <dependency>
            <groupId>org.json</groupId>
            <artifactId>json</artifactId>
            <version>20211205</version>
        </dependency>
```

- Ya con la libreria podemos trabajar con los string que tienen formato tipo json de la siguiente forma:

- Se puede trabajar con una clase a parte y con lombok se crean los getter, setter y el constructor

- En un metodo publico se puede trabajar como en el siguiente ejemplo:

```java
import lombok.Data;
import org.json.JSONArray;
import org.json.JSONObject;

@Data
public class JsonFileTest {

    private String line = "[{\"username\":\"tomsmith\",\"password\":\"SuperSecretPassword!\",\"url\":\"https://the-internet.herokuapp.com\"}]";

    public String checkResource(String jsonElement) {
        JSONArray recs = new JSONArray(getLine());
        for (Object data : recs) {
            JSONObject obj = ((JSONObject) data);
            jsonElement = obj.getString(jsonElement);
        }
        return jsonElement;
    }
}
```

- Con esto se logra poner el archivo tipo json como un array y despues como un objeto que puede ser llamado segun el return desde otra clase de esta forma:

- En el JSON los datos que se tiene son: username, password y url que pueden ser llamados instanciando la clase y creando un objeto de la clase;

```java
JsonFileTest jsonfile = new JsonFileTest();

        driver.get(jsonfile.checkResource("url"));

        loginpage.addUserName(jsonfile.checkResource("username"));
        loginpage.addPassword(jsonfile.checkResource("password"));

```
