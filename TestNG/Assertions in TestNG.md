# Assertions in TestNG

- Check this [LINK](https://www.seleniumeasy.com/testng-tutorials/assertions-in-testng)

- More examples in this [link](https://www.javadoc.io/doc/org.testng/testng/6.8.17/org/testng/Assert.html)

---

- What is Assertion????

* Asserts helps us to verify the conditions of the test and decide whether test has failed or passed. A test is considered successful ONLY if it is completed without throwing any exception. There is a difference between SoftAssert and Hard Assert.

* Let us focus more on using Assertions (Hard assert). Also check SoftAssert example in TestNG for more details on soft asserts.

* Here we are verifying if the page title is equal to 'Google' or not. If the page title is not matching with the text / title that we provided, it will fail the test case.

* To explain you what is assertion, lets us look into below code sample

```java
@Test
	public void testCaseVerifyHomePage() {
		driver= new FirefoxDriver();
		driver.navigate().to("http://google.com");
		Assert.assertEquals("Google", driver.getTitle());
	}
```

## Like wise there are many Assertions provided by the TestNG. The below are the few which are used commonly.

- assertEqual

```text
assertEqual(String actual,String expected) :- It takes two string arguments and checks whether both are equal, if not it will fail the test.

assertEqual(String actual,String expected, String message) :- It takes three string arguments and checks whether both are equal, if not it will fail the test and throws the message which we provide.

assertEquals(boolean actual,boolean expected) :- It takes two Boolean arguments and checks whether both are equal, if not it will fail the test.

assertEquals(java.util.Collection actual, java.util.Collection expected, java.lang.String message) :- Takes two collection objects and verifies both collections contain the same elements and with the same order. if not it will fail the test with the given message.
```

- assertNull –

This assertion checks if the object is null or not. It aborts the test if object is null and gives an exception.

```text
Assert.assertNull(object);
```

- assertNotNull –

This assertion checks if object is null or not. It aborts the test if object is not null that is if object is having any value and gives an exception.

```text
Assert.assertNotNull(object);
```

- assertTrue

```text
Assert.assertTrue(condition) :- It takes one boolean arguments and checks that a condition is true, If it isn't, an AssertionError is thrown.

Assert.assertTrue(condition, message) :- It takes one boolean argument and String message. It Asserts that a condition is true. If it isn't, an AssertionError, with the given message, is thrown.
```

- assertNotEquals

```text
Assert.assertNotEquals(actual, expected, message;
```

- assertFalse

```text
Assert.assertFalse(condition) :- It takes one boolean arguments and checks that a condition is false, If it isn't, an AssertionError is thrown.

Assert.assertFalse(condition, message) :- It takes one boolean argument and String message. It Asserts that a condition is false. If it isn't, an AssertionError, with the given message, is thrown.
```

## The below is the sample code to use assertions :

```java
@Test
	public void testCaseVerifyHomePage() {
		driver= new FirefoxDriver();
		driver.navigate().to("http://google.com");
		Assert.assertEquals("Gooogle", driver.getTitle(), "Strings are not matching");
		//Write a code to login and write a method called isUserLoggedInSuccessfully and isUserLoggedOut which returns boolean.
		Assert.assertTrue(isUserLoggedInSuccessfully(), "User failed to login");
		Assert.assertFalse(isUserLoggedOut())
		}
}
```

- Soft Assertion :

These types of Assertions are the type of assertions do not throw an exception when an assertion fails and continues with the next step after the assert statement.
