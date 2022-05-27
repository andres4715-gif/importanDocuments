# Condicionales:

## if...else

### Validar estos links:

[w3schools](https://www.w3schools.com/js/js_if_else.asp)

```javascript
In JavaScript we have the following conditional statements:

Use if to specify a block of code to be executed, if a specified condition is true
Use else to specify a block of code to be executed, if the same condition is false
Use else if to specify a new condition to test, if the first condition is false
Use switch to specify many alternative blocks of code to be executed

- Example:

    getScale(): void {
        if (platformName === 'and') {
            const androidScale = this.andFahrenheit.getAttribute('content-desc');
            console.log('Android', androidScale);
        } else {
            const iosScale = this.iosFahrenheit.getAttribute('value');
            console.log('ios', iosScale);
        }
    }
```

## Conditional (ternary) operator in JavaScript

- If you have a short if else statement, then you might choose to go with the ternary operator. The word ternary means something composed of three parts.

This is the basic syntax for a ternary operator:

```javascritp
condition ? if condition is true : if condition is false
```

- The condition goes before the ? mark and if it is true, then the code between the ? mark and : would execute. If the condition is false, then the code after the : would execute.

In this example, since age is greater than 18, then the message to the console would be "Can vote".

```javascript
const age = 32;
const citizen = age >= 18 ? "Can vote" : "Cannot vote";
console.log(citizen);
```

- Ejemplo:

```javascript
    getCountry(): string {
        getValueAndCompareWithAccesibilityId(platformName, SELECTORS.REGION, Region.regions.Americas[0].Americas, 'Selected Region');
        const country = platformName === 'and' ? this.region.getAttribute("content-desc") : this.region.getAttribute("value");
        return country;
    }
```
