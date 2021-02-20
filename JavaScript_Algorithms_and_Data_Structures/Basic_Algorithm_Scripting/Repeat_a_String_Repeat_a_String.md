------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function repeatStringNumTimes(str, num) {
  let strRepeated = '';
  while(num > 0) {
    strRepeated += str;
    num--;
  }
  return strRepeated;
}

repeatStringNumTimes("abc", 3);
```
---

## Problem
### Repeat a String Repeat a String
Repeat a given string str (first argument) for num times (second argument). Return an empty string if num is not a positive number. For the purpose of this challenge, do not use the built-in .repeat() method.
