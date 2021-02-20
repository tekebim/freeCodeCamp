------
Created by Michael R. Year : 2021 - 19/02/2021 Personal learning courses
------

## My solution

```javascript
function factorialize(num) {
  // test if num equal 0 or 1
  if(num === 0 || num ===1){
    return 1
  }
  // loop decrement
  for (let i = num -1 ; i > 1; i--){
    num *= i
  }
  return num;
}

factorialize(5);
```

---

## Problem
### Factorialize a Number
Return the factorial of the provided integer.

If the integer is represented with the letter n, a factorial is the product of all positive integers less than or equal to n.

Factorials are often represented with the shorthand notation `n!`

For example: `5! = 1 * 2 * 3 * 4 * 5 = 120`

Only integers greater than or equal to zero will be supplied to the function.
``
