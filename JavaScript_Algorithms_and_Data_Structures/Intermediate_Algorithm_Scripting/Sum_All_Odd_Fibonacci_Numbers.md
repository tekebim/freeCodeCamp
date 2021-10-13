Created by Michael R. Year : 2021 - 12/10/2021 Personal learning courses

```
Sum All Odd Fibonacci Numbers

Given a positive integer num, return the sum of all odd Fibonacci numbers that are less than or equal to num.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, sumFibs(10) should return 10 because all odd Fibonacci numbers less than or equal to 10 are 1, 1, 3, and 5.
```

## My solution 1

```javascript
function sumFibs(num) {
  let values = [0, 1];

  function suitFibonacci(previousValue, currentValue) {
    return previousValue + currentValue;
  }

  function sumAll(array) {
    return array
      .filter(value => value % 2 !== 0)
      .reduce((acc, current) => acc + current)
  }

  for (let i = 1; i <= num; i++) {
    let value = suitFibonacci(values[i - 1], values[i]);
    if (value > num) {
      break
    }
    values.push(value);
  }
  return sumAll(values);
}

sumFibs(10);
```

```javascript
function sumFibs(num) {
  let fibonacciSequence = [0, 1];
  let counter = fibonacciSequence[fibonacciSequence.length - 2] + fibonacciSequence[fibonacciSequence.length - 1];

  function sumAll(array) {
    return array
      .filter(value => value % 2 !== 0)
      .reduce((acc, current) => acc + current)
  }

  while (counter <= num) {
    fibonacciSequence.push(counter);
    counter = fibonacciSequence[fibonacciSequence.length - 2] + fibonacciSequence[fibonacciSequence.length - 1];
  }

  return sumAll(fibonacciSequence);
}

sumFibs(10);
```
