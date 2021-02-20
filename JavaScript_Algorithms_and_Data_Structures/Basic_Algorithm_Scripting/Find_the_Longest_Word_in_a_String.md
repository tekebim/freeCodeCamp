------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution #1

```javascript
function findLongestWordLength(str) {
  // Split each string on array
  let arr = str.split(' ');
  // Define the max string lentgh
  let maxStr = 0;
  // Loop on each string of array
  for (let i = 0; i < arr.length; i++){
    // If bigger than max
    if(arr[i].length > maxStr){
      // Set as the max
      maxStr = arr[i].length
    }    
  }
  return maxStr;
}

findLongestWordLength("The quick brown fox jumped over the lazy dog");
```

## My solution #2

```javascript
function findLongestWordLength(str) {  
  let strLongest = str.split(' ').reduce(function(longest, current){
    return current.length > longest.length ? current : longest;
  })
  return strLongest.length;
}
```
---

## Problem
### Find the Longest Word in a String
Return the length of the longest word in the provided sentence.

Your response should be a number.

