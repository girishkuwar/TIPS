# JavaScript Arrays

An array is a special variable, which can hold more than one value:

```javascript
const cars = ["Saab", "Volvo", "BMW"];
```

You can also create an array, and then provide the elements:

```javascript
const cars = [];
cars[0]= "Saab";
cars[1]= "Volvo";
cars[2]= "BMW";
```

## Converting an Array to a String

The JavaScript method `toString()` converts an array to a string of (comma separated) array values.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.toString();
```

## Access the Full Array

With JavaScript, the full array can be accessed by referring to the array name:

```javascript
const cars = ["Saab", "Volvo", "BMW"];
document.getElementById("demo").innerHTML = cars;
```

## Looping Array Elements

One way to loop through an array, is using a `for` loop:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fLen = fruits.length;

let text = "<ul>";
for (let i = 0; i < fLen; i++) {
  text += "<li>" + fruits[i] + "</li>";
}
text += "</ul>";
```

You can also use the `Array.forEach()` function:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];

let text = "<ul>";
fruits.forEach(myFunction);
text += "</ul>";

function myFunction(value) {
  text += "<li>" + value + "</li>";
}
```



## JavaScript Array join()

The `join()` method also joins all array elements into a string.

It behaves just like `toString()`, but in addition you can specify the separator:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * ");
```

## JavaScript Array pop()

The `pop()` method removes the last element from an array:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();
```

## JavaScript Array push()

The `push()` method adds a new element to an array (at the end):

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");
```

## JavaScript Array shift()

The `shift()` method removes the first array element and "shifts" all other elements to a lower index.

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.shift();
```

The `shift()` method returns the value that was "shifted out":

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let fruit = fruits.shift();
```



____



## Merging Arrays (Concatenating)

In programming languages, concatenation means joining strings end-to-end.

Concatenation "snow" and "ball" gives "snowball".

Concatenating arrays means joining arrays end-to-end.

------

## JavaScript Array concat()

The `concat()` method creates a new array by merging (concatenating) existing arrays:

```javascript
const myGirls = ["Cecilie", "Lone"];
const myBoys = ["Emil", "Tobias", "Linus"];
const myChildren = myGirls.concat(myBoys);
```

### Example (Merging Three Arrays)

```javascript
const arr1 = ["Cecilie", "Lone"];
const arr2 = ["Emil", "Tobias", "Linus"];
const arr3 = ["Robin", "Morgan"];
const myChildren = arr1.concat(arr2, arr3);
```

The `concat()` method can also take strings as arguments:

```javascript
const arr1 = ["Emil", "Tobias", "Linus"];
const myChildren = arr1.concat("Peter"); 
```

## Array copyWithin()

The `copyWithin()` method copies array elements to another position in an array:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.copyWithin(2, 0);
```



## Splicing and Slicing Arrays

## JavaScript Array splice()

The `splice()` method can be used to add new items to an array:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```

The first parameter (2) defines the position **where** new elements should be **added** (spliced in).

The second parameter (0) defines **how many** elements should be **removed**.

The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be **added**.

The `splice()` method returns an array with the deleted items:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 2, "Lemon", "Kiwi");
```

## Using splice() to Remove Elements

With clever parameter setting, you can use `splice()` to remove elements without leaving "holes" in the array:

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(0, 1);
```

## JavaScript Array toSpliced()

[ES2023](https://www.w3schools.com/js/js_2023.asp) added the Array toSpliced() method as a safe way to splice an array without altering the original array.

The difference between the new **toSpliced()** method and the old **splice()** method is that the new method creates a new array, keeping the original array unchanged, while the old method altered the original array.

```javascript
const months = ["Jan", "Feb", "Mar", "Apr"];
const spliced = months.toSpliced(0, 1);
```

## JavaScript Array slice()

The `slice()` method slices out a piece of an array into a new array:

```javascript
// Slice out a part of an array starting from array element 1 ("Orange"):
const fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
const citrus = fruits.slice(1);
```

## JavaScript Array indexOf()

The `indexOf()` method searches an array for an element value and returns its position.

```javascript
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.indexOf("Apple") + 1;
```

## JavaScript Array lastIndexOf()

`Array.lastIndexOf()` is the same as `Array.indexOf()`, but returns the position of the last occurrence of the specified element.

```javascript
const fruits = ["Apple", "Orange", "Apple", "Mango"];
let position = fruits.lastIndexOf("Apple") + 1;
```

## JavaScript Array includes()

ECMAScript 2016 introduced `Array.includes()` to arrays. This allows us to check if an element is present in an array (including NaN, unlike indexOf).

```javascript
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.includes("Mango"); // is true
```

## JavaScript Array find()

The `find()` method returns the value of the first array element that passes a test function.

This example finds (returns the value of) the first element that is larger than 18:

```javascript
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```



## JavaScript Array findIndex()

The `findIndex()` method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

```javascript
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```













