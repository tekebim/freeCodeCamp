Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Steamroller
Flatten a nested array. You must account for varying levels of nesting.
```

## My solution 1

```javascript
function steamrollArray(arr) {
  let result = [];
  arr.forEach(item => {
    if (Array.isArray(item)) {
      result = [...result, ...steamrollArray(item)];
    } else {
      result.push(item);
    }
  });
  return result;
}

steamrollArray([1, [], [3, [[4]]]])
```
