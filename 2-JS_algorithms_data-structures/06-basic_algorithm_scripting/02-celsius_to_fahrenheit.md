# Convert Celsius to Fahrenheit

**NOTE**: The algorithm to convert from Celsius to Fahrenheit is the temperature in Celsius times 9/5, plus 32.

```javascript
function convertToF(celsius) {
  let fahrenheit = celsius * 9/5 + 32;
  // console.log(fahrenheit);
  return fahrenheit;
}

convertToF(30);
```