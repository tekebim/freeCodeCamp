t------
Created by Michael R. Year : 2021 - 25/02/2021 Personal learning courses
------

## My solution 1

```javascript
function diffArray(arr1, arr2) {
  let diffArray = [];
  // Function which need two arrays to compare
  const findItemOnce = (firstArr, secondArr) => {
    // Loop with map on each element of the first array
    firstArr.map((item) => {
      // If this element not found in any second array's index
      // Push to diffArray
      secondArr.indexOf(item) < 0 && diffArray.push(item)
    })
  }
  // Try to find unique value in array 1
  findItemOnce(arr1, arr2)
  // Try to find unique value in array 2
  findItemOnce(arr2, arr1)
  // Return the diff array
  return diffArray
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```
## My solution 2

```javascript
function diffArray(arr1, arr2) {
let arrMerged = arr1.concat(arr2)  
let diffArray = arrMerged.filter(
el => arr1.indexOf(el) === -1 || arr2.indexOf(el) === -1    
)
return diffArray;
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```
---

## Problem
### Diff Two Arrays
Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

Note
You can return the array with its elements in any order.
