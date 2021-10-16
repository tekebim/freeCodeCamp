Created by Michael R. Year : 2021 - 14/10/2021 Personal learning courses

```
Caesars Cipher
One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount.

A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus A ↔ N, B ↔ O and so on.

Write a function which takes a ROT13 encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on.
```

## Solution 1

```javascript
function rot13(str) {
  let alphabetStr = 'abcdefghijklmnopqrstuvwxyz';
  let alphabet = alphabetStr.toUpperCase().split('');
  let max = alphabet.length;
  let step = 13;
  let result = "";
  let input = str.split("");

  input.map(letter => {
    if(!letter.match(/[A-Z]/)){
      result += letter;
    }
    else {
      let currentIndex = alphabet.indexOf(letter);
      if((currentIndex + step) < max){
        result += alphabet[currentIndex + step];
      }
      else {
        result += alphabet[((currentIndex + step) - max)];
      }
    }
  });

  return result;
}

rot13("SERR PBQR PNZC");
```
