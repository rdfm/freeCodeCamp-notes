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

Chaining the three methods together:

```javascript
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

- can be a decrementing or incrementing loop

```javascript
let reverse = (str) => {
  let reversed = "";
  for (var i = str.length - 1; i >= 0; i--){
    reversed += str[i];
  }
  return reversed;
}
```

### ES6: for...of

```javascript
let reverse = (str) => {
    let reversed = "";
        for(let char of str){
        console.log(reversed);
        reversed = char + reversed;
    };
    return reversed;
}
```

## 2. reverse() method for arrays

```javascript
function reverse(str){
  return str.split("").reverse().join("");
}
```

## 3. spread syntax (ES6) + reverse() method for arrays

**...** (spread operator)

```javascript
function reverse(str){
  return [...str].reverse().join('');
}
```

## 4. reduce() method for arrays

```javascript
function reverse(str){
  return str.split("").reduce((rev, char)=> char + rev, '');
}
```

## 5. recursion

```javascript
function reverse(str){
 if(str === ""){
  return str
 }else{
  return reverse(str.substr(1)) + str[0]
 }
}
```

Refactor (use ternary operator):

```javascript
function reverse(str){
 return str ? reverse(str.substr(1)) + str[0] : str
}
```
