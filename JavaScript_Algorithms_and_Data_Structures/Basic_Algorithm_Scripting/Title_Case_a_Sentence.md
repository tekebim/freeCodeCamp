------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function titleCase(str) {
  // First split each words on array
  let wordsArray = str.split(' ');
  // Loop on each entry on wordsArray
  for(let i=0; i < wordsArray.length; i++){
    // Replace the value
    // Get the first character and uppercase, then lowercase the rest
    wordsArray[i] = wordsArray[i].charAt(0).toUpperCase() + wordsArray[i].slice(1).toLowerCase();
  }
  // return the words array as a string
  return wordsArray.join(' ');
}

titleCase("I'm a little tea pot");
```
---

## Problem
### Title Case a Sentence
Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".
