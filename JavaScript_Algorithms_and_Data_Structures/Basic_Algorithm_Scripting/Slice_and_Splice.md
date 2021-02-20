------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function frankenSplice(arr1, arr2, n) {
  // Copy the arr2 into new array to prevent modification
  let arrMerged = [...arr2];
  // For each value inside arr1, add the the value into the arr2 based on the index position n + current item index
  for(let i=0; i<arr1.length; i++){
    arrMerged.splice(n+i, 0, arr1[i])
  }
  return arrMerged;
}

frankenSplice([1, 2, 3], [4, 5, 6], 1);
```
---

## Problem
### Slice and Splice
You are given two arrays and an index.

Copy each element of the first array into the second array, in order.

Begin inserting elements at index `n` of the second array.

Return the resulting array. The input arrays should remain the same after the function runs.
