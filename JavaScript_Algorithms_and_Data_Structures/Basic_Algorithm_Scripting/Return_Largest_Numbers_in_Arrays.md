------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function largestOfFour(arr) {
  // Define array which contains result of each maximum value
  let arrMax = [];
  // Loop on each sub array
  for(let i=0; i < arr.length; i++){    
    // Set the default numberMax as the first sub array value
    let numberMax = arr[i][0];
    // For each value of this sub array
    for(let n=0; n < arr[i].length; n++){
      // If current value is sup
      if(arr[i][n] > numberMax){
        // Set as the new maximum
        numberMax = arr[i][n];
      }
    }
    // Push current sub array's maximum on arrayMax 
    arrMax.push(numberMax)
  }
  return arrMax;
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```
---

## Problem

### Return Largest Numbers in Arrays
Return an array consisting of the largest number from each provided sub-array. For simplicity, the provided array will contain exactly 4 sub-arrays.

Remember, you can iterate through an array with a simple for loop, and access each member with array syntax arr[i].
