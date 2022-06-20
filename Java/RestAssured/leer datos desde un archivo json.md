# Leyendo datos desde un Json:

Si tenemos un archivo Json en una ruta del proyecto:

Para este ejemplo esta en la ruta:

```text
src/test/java/fileResources/jsonFiles/us/JsonParams.json
```

El archivo Json es:

```json
{
  "us": [
    {
      "countryCode": "us",
      "language": "(language:en)",
      "type": "(type:assets)",
      "country": "(country:us)"
    }
  ]
}
```

Para leer el archivo json se hace con este codigo:

```java
import java.io.FileReader;

import org.json.simple.JSONArray;
import org.json.simple.JSONObject;
import org.json.simple.parser.JSONParser;

public class App {
    public static void main(String[] args) throws Exception {
        JSONParser parser = new JSONParser();
        FileReader reader = new FileReader("src/test/java/fileResources/jsonFiles/us/JsonParams.json");
        Object obj = parser.parse(reader);
        JSONObject pJsonObj = (JSONObject) obj;
        JSONArray array = (JSONArray) pJsonObj.get("us");

        for (int i = 0; i < array.size(); i++) {
            JSONObject Language = (JSONObject) array.get(i);
            JSONObject Type = (JSONObject) array.get(i);
            JSONObject Country = (JSONObject) array.get(i);

            String language = (String) Language.get("language");
            String type = (String) Type.get("type");
            String country = (String) Country.get("country");

            System.out.println("the language is: " + language);
            System.out.println("the type is: " + type);
            System.out.println("the country is: " + country);
        }
    }
}
```

El output de la ejecución es:

```shell
the language is: (language:en)
the type is: (type:assets)
the country is: (country:us)
```
