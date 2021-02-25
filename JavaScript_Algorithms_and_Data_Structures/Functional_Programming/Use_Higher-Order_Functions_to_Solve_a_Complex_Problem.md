------
Created by Michael R. Year : 2021 - 24/02/2021 Personal learning courses
------

## My solution 1

```javascript
const squareList = arr => {
  // Only change code below this line
  const positiveIntegers = arr
    .filter(item => item > 0 && Number.isInteger(item))
    .map(item => item * item)

  return positiveIntegers;
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```
---

## My solution 2

```javascript
const squareList = arr => {
  // Only change code below this line

  const positiveIntegers = arr.reduce((squareInt, item) => {
    return (Number.isInteger(item) && item > 0)
      ? squareInt.concat(item * item)
      : squareInt
  },[]);

  return positiveIntegers;
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```
---

## Problem
### Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem
Now that you have worked through a few challenges using higher-order functions like map(), filter(), and reduce(), you now get to apply them to solve a more complex challenge.

We have defined a function named squareList. You need to complete the code for the squareList function using any combination of map(), filter(), and reduce() so that it returns a new array containing only the square of only the positive integers (decimal numbers are not integers) when an array of real numbers is passed to it. An example of an array containing only real numbers is [-3, 4.8, 5, 3, -3.2].

Note: Your function should not use any kind of for or while loops or the forEach() function
