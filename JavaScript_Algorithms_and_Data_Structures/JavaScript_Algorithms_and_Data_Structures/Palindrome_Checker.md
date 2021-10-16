Created by Michael R. Year : 2021 - 14/10/2021 Personal learning courses

```
Palindrome Checker
Return true if the given string is a palindrome. Otherwise, return false.

A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

Note: You'll need to remove all non-alphanumeric characters (punctuation, spaces and symbols) and turn everything into the same case (lower or upper case) in order to check for palindromes.

We'll pass strings with varying formats, such as racecar, RaceCar, and race CAR among others.

We'll also pass strings with special symbols, such as 2A3*3a2, 2A3 3a2, and 2_A3*3#A2.
```

## Solution 1

```javascript
function palindrome(str) {
  const regex = /[a-zA-Z\d]/g;

  const onlyLettersFromStr = str.match(regex);
  let lettersJoined = onlyLettersFromStr.join('').toLowerCase();
  let lettersReversed = onlyLettersFromStr.reverse().join('').toLowerCase();

  if (lettersJoined !== lettersReversed) {
    return false;
  }
  return true;
}

let result = palindrome("0_0 (: /-\ :) 0-0");
```
