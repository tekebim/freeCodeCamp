Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Sum All Primes

A prime number is a whole number greater than 1 with exactly two divisors: 1 and itself. For example, 2 is a prime number because it is only divisible by 1 and 2. In contrast, 4 is not prime since it is divisible by 1, 2 and 4.

Rewrite sumPrimes so it returns the sum of all prime numbers that are less than or equal to num.
```

## My solution 1

```javascript
function sumPrimes(num) {
  let sum = 0;

  function isPrimeNumber(number) {
    for (let j = 2; j < number; j++) {
      if (number % j === 0) {
        return false;
      }
    }
    return true;
  }

  for (let i = 2; i <= num; i++) {
    if (isPrimeNumber(i)) {
      sum += i;
    }
  }

  return sum;
}

sumPrimes(10);
```
