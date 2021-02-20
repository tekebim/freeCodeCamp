------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function mutation(arr) {
  let arrFiltered = arr.map(item => item.toLowerCase());
  for(let i=0; i < arrFiltered[1].length; i++){
    if(arrFiltered[0].indexOf(arrFiltered[1][i]) < 0) {
      return false
    }
  }
  return true
}

// mutation(["hello", "Hello"])
mutation(["hello", "hey"]);
```
---

## Problem
### Mutations
Return true if the string in the first element of the array contains all of the letters of the string in the second element of the array.

For example, `["hello", "Hello"]`, should return `true` because all of the letters in the second string are present in the first, ignoring case.

The arguments `["hello", "hey"]` should return `false` because the string "hello" does not contain a "y".

Lastly, `["Alien", "line"]`, should return `true` because all of the letters in "line" are present in "Alien".
