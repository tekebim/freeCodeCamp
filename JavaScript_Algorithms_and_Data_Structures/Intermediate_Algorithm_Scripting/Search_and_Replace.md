Created by Michael R. Year : 2021 - 11/10/2021 Personal learning courses

```
Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

Note: Preserve the case of the first character in the original word when you are replacing it. For example if you mean to replace the word Book with the word dog, it should be replaced as Dog
```

## My solution 1

```javascript
function myReplace(str, before, after) {
  if (before.charAt(0) === before.charAt(0).toUpperCase()) {
    after = after.charAt(0).toUpperCase() + after.slice(1);
  } else {
    if (after.charAt(0) === after.charAt(0).toUpperCase()) {
      after = after.charAt(0).toLowerCase() + after.slice(1);
    }
  }

  return str.replace(before, after);
}

myReplace("Let us go to the store", "store", "mall");
```

## Solution 2

```javascript
function myReplace(str, before, after) {
  let strCollection = str.split(" ");

  function isWordCapitalized(word) {
    return word[0] === word[0].toUpperCase()
  }

  function capitalizeWord(word) {
    return word[0].toUpperCase() + word.slice(1);
  }

  function lowercaseWord(word) {
    return word[0].toLowerCase() + word.slice(1);
  }

  return strCollection.map((word) => {
    if (word === before) {
      if (isWordCapitalized(word)) {
        after = capitalizeWord(after);
      } else {
        if (isWordCapitalized(after)) {
          after = lowercaseWord(after);
        }
      }
      return after;
    }
    return word;
  }).join(" ");
}
```
