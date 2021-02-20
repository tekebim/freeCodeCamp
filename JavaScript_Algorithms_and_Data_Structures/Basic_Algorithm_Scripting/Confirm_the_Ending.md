------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function confirmEnding(str, target) {  
  return str.slice(-(target.length)) === target   
}

confirmEnding("Bastian", "n");
```
---

## Problem
###Confirm the Ending
Check if a string (first argument, str) ends with the given target string (second argument, target).

This challenge can be solved with the .endsWith() method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.
