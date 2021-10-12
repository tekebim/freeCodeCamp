Created by Michael R. Year : 2021 - 26/02/2021 Personal learning courses

> Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.

## My solution 1

```javascript
function spinalCase(str) {
  let newStr = [];

  for (let i = 0; i < str.length; i++) {
    let currentLetter = str.charAt(i);
    if (str.charAt(i).match(/^[A-Z]*$/)) {
      if (i !== 0 && str.charAt(i - 1) !== ' ' && str.charAt(i - 1) !== '_') {
        newStr.push('-' + currentLetter.toLowerCase());
      } else {
        newStr.push(currentLetter.toLowerCase());
      }
    } else if (currentLetter === '_' || currentLetter === ' ') {
      newStr.push('-');
    } else {
      newStr.push(str.charAt(i));
    }
  }
  return newStr.join('');
}

spinalCase('This Is Spinal Tap');
```

## Optimized solution

```javascript
function spinalCase(str) {
  let camelCaseHandle = str.replace(/([a-z])([A-Z])/g, "$1 $2");
  let convertedStr = camelCaseHandle.replace(/\s|_/g, "-");
  convertedStr = convertedStr.toLowerCase();
  return convertedStr;
}

spinalCase('This Is Spinal Tap');
```
