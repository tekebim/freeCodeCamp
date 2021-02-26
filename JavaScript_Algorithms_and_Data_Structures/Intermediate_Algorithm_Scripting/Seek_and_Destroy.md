t------
Created by Michael R. Year : 2021 - 26/02/2021 Personal learning courses
------

## My solution 1

```javascript
function destroyer(...arr) {
  // Get the main array to test as the first argument index
  let mainArr = arr[0];
  // Get the array of value to test
  let valuesToRemove = arr.slice(1)
  // Filter on the main array if the value exist on the valuesToRemove's array
  return mainArr.filter(
    currentVal => !valuesToRemove.includes(currentVal)
  )
}

destroyer([1, 2, 3, 1, 2, 3], 2, 3);
```

---

## Problem
### Seek and Destroy
You will be provided with an initial array (the first argument in the destroyer function), followed by one or more arguments. Remove all elements from the initial array that are of the same value as these arguments.

Note
You have to use the arguments object.
