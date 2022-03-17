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
