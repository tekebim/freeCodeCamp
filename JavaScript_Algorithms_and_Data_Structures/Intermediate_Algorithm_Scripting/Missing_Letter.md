Created by Michael R. Year : 2021 - 12/10/2021 Personal learning courses

```
Missing letters

Find the missing letter in the passed letter range and return it.
If all letters are present in the range, return undefined.
```

## My solution 1

```javascript
function fearNotLetter(str) {
  let alphabetStr = "abcdefghijklmnopqrstuvwxyz";
  let alphabetArr = alphabetStr.split("");
  let firstLetter = str.slice(0, 1);
  let lastLetter = str.slice(-1);
  let firstLetterPos = alphabetArr.indexOf(firstLetter);
  let lastLetterPos = alphabetArr.indexOf(lastLetter);
  let rangeLetters = alphabetArr.slice(firstLetterPos, lastLetterPos + 1);
  let inputLetters = str.split("");
  let missingLetters = [];

  rangeLetters.filter(letter => {
    if (!inputLetters.includes(letter)) {
      missingLetters.push(letter);
    }
  });

  return missingLetters.length === 0 ? undefined : missingLetters.join("");
}

fearNotLetter("abce");
```
