# Reverse a String

**ARTICLE**: [Three Ways to Reverse a String in JavaScript](https://www.freecodecamp.org/news/how-to-reverse-a-string-in-javascript-in-3-different-ways-75e4763c68cb/)

## 1. Reverse a String With Built-In Functions

```javascript
function reverseString(str) {
  var splitString = str.split("");
  var reverseArray = splitString.reverse();
  var joinArray = reverseArray.join("");
  return joinArray;
}
reverseString("hello");
```

```javascript
Chaining the three methods together:

function reverseString(str) {
    return str.split("").reverse().join("");
}
reverseString("hello");
```

## 2. Reverse a String With a Decrementing For Loop

```javascript
function reverseString(str) {
    var newString = "";
    for (var i = str.length - 1; i >= 0; i--) {
        newString += str[i];
    }
    return newString;
}
reverseString('hello');
```

## 3. Reverse a String With Recursion

```javascript
function reverseString(str) {
  if (str === "")
    return "";
  else
    return reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```

**Conditional (Ternary) Operator**:

```javascript
function reverseString(str) {
  return (str === '') ? '' : reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```

---

**ARTICLE**: [5 ways to reverse a string in Javascript](https://medium.com/quick-code/5-ways-to-reverse-a-string-in-javascript-466f62845827)

## 1. for loop

```javascript

```

```javascript

```

## 2. reverse() method for arrays

```javascript

```

## 3. spread syntax (ES6) + reverse() method for arrays

```javascript

```

## 4. reduce() method for arrays

```javascript

```

## 5. recursion

```javascript

```