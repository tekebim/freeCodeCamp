------
Created by Michael R. Year : 2021 - 19/02/2021 Personal learning courses
------

## My solution
```javascript
function reverseString(str) {
  // create a buffer array
  let buffer = [];
  // split each letter on string
  for(let i=0; i < str.length; i++){
    // push the letter at start of buffer array
    buffer.unshift(str[i])
  }
  // convert buffer array to string
  str = buffer.join('') + "";
  return str;
}

reverseString("hello");
```

---

## Problem
Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.
