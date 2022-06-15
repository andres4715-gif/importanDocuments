# RestAssured with duplicate query parameters

- Este aplica cuando en el enpoint tenemos varios query parametros con el mismo nombre.

Ejemplo:

```link
https://api-stage.firestonebpco.com/solr/site_search/select?q=roof&fq=(country:us)&fq=(language:en)&fq=(type:assets)&rows=10&facet.field=documentType
```

Que es lo que esta pasando,

Que el endpoint tiene muchos parametros pero tres de ellos tienen el mismo nombre: **fq**, por ese motivo cuando vamos a enviar con restAssured los queriy parametros el sistema solo toma uno de ellos ya que, restAssured toma los query parametros desde un mapa.

- Que se hace en ese caso?.

1. Importar desde java

```java
import java.util.Arrays;
```

2. Utilizar el metodo:

```java
Arrays.asList()
```

3. Agregar los query parametros como Arrays dentro del Mapa.

Example:

```java
    public static HashMap withQueryParam() {
        HashMap<String, Object> validUser = new HashMap<>();
        validUser.put("q", "roof");
        validUser.put("fq", Arrays.asList("(country:us)", "(language:en)", "(type:assets)"));
        validUser.put("rows", 10);
        validUser.put("facet.field", "documentType");
        validUser.put("facet", true);
        return validUser;
    }
```

_FIN_
