------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function chunkArrayInGroups(arr, size) {
  let arrSplitted = [];
  for (let i = 0; i < arr.length; i += size) {
    arrSplitted.push(arr.slice(i, i + size));
  }
  return arrSplitted;
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```
---

## Problem
### Chunky Monkey
Write a function that splits an array (first argument) into groups the length of size (second argument) and returns them as a two-dimensional array.
