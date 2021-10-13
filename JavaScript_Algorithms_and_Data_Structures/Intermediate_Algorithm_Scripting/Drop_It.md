Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Given the array arr, iterate through and remove each element starting from the first element (the 0 index) until the function func returns true when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, arr should be returned as an empty array.
```

## My solution 1

```javascript
function dropElements(arr, func) {

  let result = [];

  for (let i = 0; i <= arr.length; i++) {
    if (func(arr[i])) {
      result = arr.slice(i)
      break;
    }
  }

  return result;
}

dropElements([1, 2, 3], function (n) {
  return n < 3;
});
```
