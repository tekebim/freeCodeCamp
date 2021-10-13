Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Arguments Optional
Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

For example, addTogether(2, 3) should return 5, and addTogether(2) should return a function.

Calling this returned function with a single argument will then return the sum:

var sumTwoAnd = addTogether(2);
sumTwoAnd(3) returns 5.

If either argument isn't a valid number, return undefined.
```

## Solution 1

```javascript
function addTogether() {
  let args = Array.from(arguments);
  let firstNumber = args[0];

  for (let i = 0; i < args.length; i++) {
    if (!checkIsNumber(args[i])) {
      return undefined;
    }
  }

  if (args.length === 2) {
    return args[0] + args[1];
  } else {
    function internalSum(number) {
      if (!checkIsNumber(number)) {
        return undefined;
      }
      return args[0] + number;
    }

    return internalSum;
  }
}

function checkIsNumber(value) {
  if (typeof (value) !== 'number') {
    return false;
  }
  return true;
}

let operation = addTogether(5)(7);
```
