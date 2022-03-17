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

    private String line =
    "[{\"username\":\"tomsmith\",\"password\":\"SuperSecretPassword!\",\"url\":\"https://the-internet.herokuapp.com\"}]";

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

## DROPDOWN

- Como manejar los dropDown

```java
- En en page lo que se hace es agregar el selector del elemento que contiene
la lista de elementos

- Luego se crea una instancia de la clase Select y con el metodo selectByVisibleText se agrega el elemento
que se requiera:

- Ejemplo:

public class DropDown {

    WebDriver driver;

    By pleaseSelectAnOptionDropDown = By.id("dropdown");

    public DropDown(WebDriver driver) {
        this.driver = driver;
    }

    public void chooseAnOptionDropDown() {
        Select option = new Select(driver.findElement(pleaseSelectAnOptionDropDown));
        option.selectByVisibleText("Option 1");
    }
}
```

## SWITCH TO OTHER TAP:

- Para hacer esto se da el click en la pagina anterior para que sea desplegado el otro TAP dentro del navegador y ya con la otro pagina abierta lo que se hace es crear un Lista de String, quedaria de esta forma:

```java

En la clase donde se esta ejecutando el test (no necesaria mente), se crea
la lista y luego se hace el llamado al metodo de Selenium: switchTo()

    ArrayList<String> newTb = new ArrayList<String>(driver.getWindowHandles();
    driver.switchTo().window(newTb.get(1));

- Depende de la necedidad seria validar que si estemos en la siguiente pagina y para esto en el page que se este
utilizandose puede crear un metodo para obtener algún texto, se podria
hacer de la siguiente forma:

    By newWindowsText = By.xpath("//h3[text() = 'New Window']");

    public String getNewWindowsText() {
        String gettingTextLabelNewPage = driver.findElement(newWindowsText).getText();
        return gettingTextLabelNewPage;
    }

- Ya seria llamar el metodo creado desde la clase donde se ejecuta el test y hacer un Assert pero eso es opcional:

Assert.assertEquals(openingnewwindowspage.getNewWindowsText(), "New Window");
```
