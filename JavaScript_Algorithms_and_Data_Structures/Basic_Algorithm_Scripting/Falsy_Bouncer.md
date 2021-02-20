------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function bouncer(arr) {
  return arr.filter(item => Boolean(item))
}

bouncer([7, "ate", "", false, 9]);
```
---

## Problem
### Falsy Bouncer
Remove all falsy values from an array.

Falsy values in JavaScript are `false`, `null`, `0`, `""`, `undefined`, and `NaN`.

Hint: Try converting each value to a Boolean.
