Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Smallest Common Multiple

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

For example, if given 1 and 3, find the smallest common multiple of both 1 and 3 that is also evenly divisible by all numbers between 1 and 3. The answer here would be 6.
```

## Solution 1

```javascript
function smallestCommons(arr) {
  let inputs = arr;

  if (inputs[0] > inputs[1]) {
    inputs = orderArgNumerical(inputs[0], inputs[1])
  }

  let minNumber = inputs[0];
  let maxNumber = inputs[1];
  let multiple = 1;

  let range = getRange(minNumber, maxNumber);

  while (multiple < 100000) {
    let higherCommonMultipleNumber = (minNumber * multiple) * maxNumber;
    let trueCount = 0;

    for (let i = 0; i < range.length; i++) {
      if (higherCommonMultipleNumber % range[i] === 0) {
        trueCount += 1;
        if (trueCount === range.length) {
          return higherCommonMultipleNumber;
        }
      }
    }

    multiple += 1;
  }
}

function orderArgNumerical(a, b) {
  if (a > b) {
    return [b, a]
  }
}

function getRange(min, max) {
  let range = []
  for (let i = min; i <= max; i += 1) {
    range.push(i);
  }
  return range;
}

smallestCommons([1, 13]);
```

## Solution 2
````javascript
function smallestCommons(arr) {
  let minNumber = Math.min(...arr);
  let maxNumber = Math.max(...arr);
  const totalDivisors = getRange(minNumber, maxNumber).length;  
  let maxBound = 1;
  for (let i = minNumber; i <= maxNumber; i++) {
    maxBound *= i;
  }

  for (let multiple = maxNumber; multiple <= maxBound; multiple += maxNumber) {
    let divisorCount = 0;
    // Check if multiple is divible by all numbers in range
    for (let i = minNumber; i <= maxNumber; i++) {
      if (multiple % i === 0) {
        divisorCount += 1;
      }
    }
    if (divisorCount === totalDivisors) {
      return multiple;
    }
  }
}

function getRange(min, max){
  let range = []
  for(let i=min; i<=max; i+=1){
    range.push(i);
  }  
  return range;
}

smallestCommons([1,3]);
````
