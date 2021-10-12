t------
Created by Michael R. Year : 2021 - 25/02/2021 Personal learning courses
------

## My solution 1

```javascript
function sumAll(arr) {
  // Sort the array ascendant
  arr.sort((a, b) => a - b)
  // Init sum value
  let sum = 0;
  // Loop for each integer between array min and array max number with step of 1
  for (let i=arr[0]; i <= arr[1]; i++){
    sum += i
  }
  return sum;
}

sumAll([1, 4]);
```
## My solution 2

```javascript
function sumAll(arr) {
  // Sort the array ascendant
  arr.sort((a, b) => a - b)
  // Create a array sorted
  let sumArr = [];
  // Push item on array sorted
  for (let i=arr[0]; i <= arr[1]; i++){
    sumArr.push(i)
  }
  // Use Array.prototype.reduce() method
  let sumAll = sumArr.reduce((accSum, current) => {
    return accSum + current
  }, 0);

  return sumAll;
}

sumAll([1, 4]);
```
---

## Problem
### Sum All Numbers in a Range
We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. The lowest number will not always come first.

For example, sumAll([4,1]) should return 10 because sum of all the numbers between 1 and 4 (both inclusive) is 10.
