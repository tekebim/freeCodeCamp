------
Created by Michael R. Year : 2021 - 20/02/2021 Personal learning courses
------

## My solution

```javascript
function truncateString(str, num) {  
  if(str.length > num){
    str = str.slice(0, num) + '...';
  }  
  return str
}

truncateString("A-tisket a-tasket A green and yellow basket", 8);
```
---

## Problem
### Truncate a String
Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a ... ending.
