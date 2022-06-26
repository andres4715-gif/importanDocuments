# Setting Parameters

- Se puede consultar la información completa en este [link](https://www.baeldung.com/rest-assured-header-cookie-parameter)

Nota Importante:

```text
No es lo mismo, enviar parametros que enviar query parametros.
```

- Este aplica si es necesario enviar un parametro: _pathParam_

Ejemplo para enviar un solo parametro:

```java
@Test
public void whenUsePathParam_thenOK() {
    given().pathParam("user", "eugenp")
      .when().get("/users/{user}/repos")
      .then().statusCode(200);
}
```

---

## Este aplica si es necesario enviar varios parametros: _pathParams_

```java
@Test
public void whenUseMultiplePathParam_thenOK() {
    given().pathParams("owner", "eugenp", "repo", "tutorials")
      .when().get("/repos/{owner}/{repo}")
      .then().statusCode(200);

    given().pathParams("owner", "eugenp")
      .when().get("/repos/{owner}/{repo}","tutorials")
      .then().statusCode(200);
}
```

- In this example, we've used named path parameters, but we can also add unnamed parameters, and even combine the two:

```java
@Test
public void whenUseMultiplePathParam_thenOK() {
given().pathParams("owner", "eugenp")
  .when().get("/repos/{owner}/{repo}", "tutorials")
  .then().statusCode(200);
}
```

The resulting URL, in this case, is:

```text
https://api.github.com/repos/eugenp/tutorials.
```

Note that the unnamed parameters are index-based.
