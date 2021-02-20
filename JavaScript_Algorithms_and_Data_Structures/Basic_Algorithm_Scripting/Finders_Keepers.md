------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function findElement(arr, func) {
  let num;
  for(let i=1; i < arr.length; i++){
    if(func(arr[i])){
      num = arr[i];
      return num;
    }
  }
  return num;
}

findElement([1, 2, 3, 4], num => num % 2 === 0);
```
---

## Problem
### Finders Keepers
Create a function that looks through an array arr and returns the first element in it that passes a 'truth test'. This means that given an element x, the 'truth test' is passed if func(x) is true. If no element passes the test, return undefined.
