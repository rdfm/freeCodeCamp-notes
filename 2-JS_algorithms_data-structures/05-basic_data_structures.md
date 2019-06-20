# freeCodeCamp (Basic Data Structures)

## Array: Collection of Data

### one-dimensional array

- one level
- NO nested arrays

EXAMPLE:

```javascript
let simpleArray = ['one', 2, 'three', true, false, undefined, null];

console.log(simpleArray.length);    // logs 7
```

**NOTE**: All arrays have a length property (Array.length)

### multi-dimensional array

- array that contains other arrays (nested)

EXAMPLE:

```javascript
let complexArray = [
  [
    {
      one: 1,
      two: 2
    },
    {
      three: 3,
      four: 4
    }
  ],
  [
    {
      a: "a",
      b: "b"
    },
    {
      c: "c",
      d: “d”
    }
  ]
];
```

---

## Bracket Notation

- each item in an array has an index
- index = position in the array

**NOTE**: JavaScript is *zero-indexed* (first element in an array is the *zeroth* position)

EXAMPLE:

```javascript
let ourArray = ["a", "b", "c"];

let ourVariable = ourArray[0];
// ourVariable equals "a"

ourArray[1] = "not b anymore";
// ourArray now equals ["a", "not b anymore", "c"];
```

---

## Add items to Array: .push() and .unshift()

**.push()** method = *ADD* items **END**

**.unshift()** method = *ADD* items **BEGINNING**

EXAMPLE:

```javascript
let twentyThree = 'XXIII';
let romanNumerals = ['XXI', 'XXII'];

romanNumerals.unshift('XIX', 'XX');
// now equals ['XIX', 'XX', 'XXI', 'XXII']

romanNumerals.push(twentyThree);
// now equals ['XIX', 'XX', 'XXI', 'XXII', 'XXIII']
```

**NOTE**: Can pass variables

---

## Remove items from Array: .pop() and .shift()

**.pop()** method = *REMOVE* items **END**

**.shift()** method = *REMOVE* items **BEGINNING**

EXAMPLE:

```javascript
let greetings = ['whats up?', 'hello', 'see ya!'];

greetings.pop();
// now equals ['whats up?', 'hello']

greetings.shift();
// now equals ['hello']
```

**NOTE**: Can return value of returned element

```javascript
let popped = greetings.pop();
// returns 'hello'
// greetings now equals []
```

---

## Remove items from Array: .splice()

**.splice()** method:

- remove any number of consecutive elements
- takes 3 parameters
  - start = index / position
  - deleteCount (optional) = number of items to delete
  - Add items (optional)
- returns an array
- [MDN: Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

EXAMPLE:

```javascript
let array = ['today', 'was', 'not', 'so', 'great'];

array.splice(2, 2);
// remove 2 elements beginning with the 3rd element
// array now equals ['today', 'was', 'great']
```

EXAMPLE (Return an array):

```javascript
let array = ['I', 'am', 'feeling', 'really', 'happy'];

let newArray = array.splice(3, 2);
// newArray equals ['really', 'happy']
```

---

## Add items to Array: .splice()

**.splice()**:

- use third parameter to add one or more elements
- quickly switching out an element (or set of elements)

EXAMPLE:

```javascript
function colorChange(arr, index, newColor) {
  arr.splice(index, 1, newColor);
  return arr;
}

let colorScheme = ['#878787', '#a08794', '#bb7e8c', '#c9b6be', '#d1becf'];

colorScheme = colorChange(colorScheme, 2, '#332327');
// we have removed '#bb7e8c' and added '#332327' in its place
// colorScheme now equals ['#878787', '#a08794', '#332327', '#c9b6be', '#d1becf']
```

---

## Copy Array items: slice()

**slice()**:

- copies or extracts a given number of elements to a new array
- original array untouched
- takes 2 parameters:
  - index begin
  - index stop

EXAMPLE:

```javascript
let weatherConditions = ['rain', 'snow', 'sleet', 'hail', 'clear'];

let todaysWeather = weatherConditions.slice(1, 3);
// todaysWeather equals ['snow', 'sleet'];
// weatherConditions still equals ['rain', 'snow', 'sleet', 'hail', 'clear']
```

---

## Copy Array (with the Spread Operator)

**...** (spread operator):

- allows to copy all of an array's elements (in order)

EXAMPLE (spread operator to copy an Array):

```javascript
let thisArray = [true, true, undefined, false, null];
let thatArray = [...thisArray];
// thatArray equals [true, true, undefined, false, null]
// thisArray remains unchanged, and is identical to thatArray
```

---

## Combine Arrays (with Spread Operator)

**...** (spread operator):

- ability to combine arrays
- aka insert all elements of one array into another (at any index)

EXAMPLE:

```javascript
let thisArray = ['sage', 'rosemary', 'parsley', 'thyme'];

let thatArray = ['basil', 'cilantro', ...thisArray, 'coriander'];
// thatArray now equals ['basil', 'cilantro', 'sage', 'rosemary', 'parsley', 'thyme', 'coriander']
```

---

## Check presence of element: indexOf()

- no guaranteeL
  - where piece of data is in an array (since arrays change / mutate)
  - if element exists

**indexOf()** method:

- built in JS method
- quickly check for presence of an element on an array
- takes element as a parameter
- returns:
  - if element present/found, returns position of element
  - if element does NOT exist, returns -1

EXAMPLE:

```javascript
let fruits = ['apples', 'pears', 'oranges', 'peaches', 'pears'];

fruits.indexOf('dates') // returns -1
fruits.indexOf('oranges') // returns 2
fruits.indexOf('pears') // returns 1, the first index at which the element exists
```

EXAMPLE (Practice):

```javascript
function quickCheck(arr, elem) {
  // change code below this line
  return (arr.indexOf(elem) === -1) ? false : true;
  // change code above this line
}

// change code here to test different cases:
console.log(quickCheck(['squash', 'onions', 'shallots'], 'mushrooms'));
```

---

## Iterate all Array items: for loop

EXAMPLE:

```javascript
function greaterThanTen(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > 10) {
      newArr.push(arr[i]);
    }
  }
  return newArr;
}

greaterThanTen([2, 12, 8, 14, 80, 0, 1]);
// returns [12, 14, 80]
```

---

## Complex multi-dimensional arrays

EXAMPLE:

```javascript
let nestedArray = [ // top, or first level - the outer most array
  ['deep'], // an array within an array, 2 levels of depth
  [
    ['deeper'], ['deeper'] // 2 arrays nested 3 levels deep
  ],
  [
    [
      ['deepest'], ['deepest'] // 2 arrays nested 4 levels deep
    ],
    [
      [
        ['deepest-est?'] // an array nested 5 levels deep
      ]
    ]
  ]
];
```

```javascript
console.log(nestedArray[2][1][0][0][0]);
// logs: deepest-est?
```

```javascript
nestedArray[2][1][0][0][0] = 'deeper still';

console.log(nestedArray[2][1][0][0][0]);
// now logs: deeper still
```

---

## Add Key-Value Pairs to JS Objects

At most basic, **objects** are a collection of key-values pairs (key aka properties)

EXAMPLE (simple object):

```javascript
let FCC_User = {
  username: 'awesome_coder',
  followers: 572,
  points: 1741,
  completedProjects: 15
};
```

EXAMPLE (use, dot notation):

```javascript
let userData = FCC_User.followers;
// userData equals 572
```

EXAMPLE (use, bracket notation):

```javascript
let userData = FCC_User['followers']
// userData equals 572
```

---

## Modify an Object (Nested within an Object)

EXAMPLE:

```javascript
let nestedObject = {
  id: 28802695164,
  date: 'December 31, 2016',
  data: {
    totalUsers: 99,
    online: 80,
    onlineStatus: {
      active: 67,
      away: 13
    }
  }
};
```

---

## Access Property Names: Bracket Notation

SYNTAX:

```javascript
let selectedFood = getCurrentFood(scannedItem);

let inventory = foods[selectedFood];
```

**NOTE**: If not present, will return *undefined*

EXAMPLE:

```javascript
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
}

function checkInventory(scannedItem) {
  return foods[scannedItem];
}

console.log(checkInventory("apples"));
```

---

## Use the delete Keyword to Remove Object Properties

**delete** Keyword: remove a key-value pair from an object

```javascript
delete foods.apples;
```

---

## Check in an Object has a Property

### hasOwnProperty()

- [MDN: Object.prototype.hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)

EXAMPLE:

```javascript
users.hasOwnProperty('Alan');

// returns true
```

### "in" operator

- [MDN: in operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in)

EXAMPLE:

```javascript
'Alan' in users;

// returns true
```

EXAMPLE:

```javascript
function isEveryoneHere(obj) {
  if (obj.hasOwnProperty('Alan') &&
    obj.hasOwnProperty('Jeff') &&
    'Sarah' in obj &&
    'Ryan' in obj ) {
      return true;
    } else {
      return false;
    }
  }
}
```

---

## Iterate Through the Keys of Object: for...in Statement

**for...in** Statement

- iterate through all the keys within an object

SYNTAX (users Object):

```javascript
for (let user in users) {
  console.log(user);
}
```

**NOTE**: Objects do not maintain an ordering to stored keys like arrays, thus a keys position on an object, or the relative order in which it appears, is irrelevant when referencing or accessing that key.

EXAMPLE:

```javascript
function countOnline(obj) {
  // change code below this line
  let online = 0;

  for(let user in obj){
    if (obj[user].online === true){
      online++;
    }
  }

  return online;
  // change code above this line
}
```

---

## Generate an Array of All Object Keys: Object.keys()

**Object.keys()** method:

- pass an object as the argument
- generate an array which contains all the keys stored in an object
- array with strings representing each key

EXAMPLE:

```javascript
function getArrayOfUsers(obj){
  return Object.keys(obj);
}
```

---

## Modify an Array Stored in an Object

**NOTE**:

- fCC Lessons: Advanced Data Structures
  - ES6: *Map* and *Set*

EXAMPLE:

```javascript
function addFriend(userObj, friend) {
  userObj['data']['friends'].push(friend);
}
```
