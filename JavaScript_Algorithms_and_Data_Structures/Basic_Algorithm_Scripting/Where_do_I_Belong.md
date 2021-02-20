------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function getIndexToIns(arr, num) {
  let lowestIndex = 0;
  // Sort the array
  let arrSorted = arr.sort((a, b) => a - b)
  // Loop on each value
  for(let i=0; i < arrSorted.length; i++){
    // If value to test is less or equal at the current index value
    if(num <= arrSorted[i]){
      return lowestIndex = i;
    }
    lowestIndex = i + 1;
  }
  return lowestIndex;
}

getIndexToIns([40, 60], 50);
```
---

## Problem
### Where do I Belong
Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

For example, `getIndexToIns([1,2,3,4], 1.5)` should return `1` because it is greater than `1` (index 0), but less than `2` (index 1).

Likewise, `getIndexToIns([20,3,5], 19)` should return `2` because once the array has been sorted it will look like `[3,5,20]` and 19 is less than `20` (index 2) and greater than 5 (index 1).
