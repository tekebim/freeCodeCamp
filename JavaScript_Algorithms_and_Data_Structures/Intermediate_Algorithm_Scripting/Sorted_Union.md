Created by Michael R. Year : 2021 - 12/10/2021 Personal learning courses

```
Sorted Union

Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.

In other words, all values present from all arrays should be included in their original order, but with no duplicates in the final array.

The unique numbers should be sorted by their original order, but the final array should not be sorted in numerical order.

Check the assertion tests for examples.
```

## My solution 1

```javascript
function uniteUnique(arr) {
  let arrUnion = [];

  [...arguments].map(array => {
    array.map(value => {
      if (arrUnion.indexOf(value) === -1) {
        arrUnion.push(value);
      }
    })
  });

  return arrUnion;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```

## Solution 2

```javascript
function uniteUnique(arr) {
  let collection = [];
  let values = Object.values(arguments);

  values.map(array => {
    array.map(value => {
      if (collection.indexOf(value) === -1) {
        collection.push(value);
      }
    })
  });

  return collection;
}
```
