# Query Parameters

Page to check some [examples](https://www.baeldung.com/rest-assured-header-cookie-parameter)

---

Example:

The param() method will act like queryParam() with GET requests.

```java
@Test
public void whenUseQueryParam_thenOK() {
    given().queryParam("q", "john").when().get("/search/users")
      .then().statusCode(200);

    given().param("q", "john").when().get("/search/users")
      .then().statusCode(200);
}
```
