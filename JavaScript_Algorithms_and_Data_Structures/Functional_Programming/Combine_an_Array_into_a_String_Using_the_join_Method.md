------
Created by Michael R. Year : 2021 - 24/02/2021 Personal learning courses
------
## My solution

```javascript
function sentensify(str) {
  // Only change code below this line
  let strSplitted = str.split(/\W/);
  return strSplitted.join(" ")
  // Only change code above this line
}
sentensify("May-the-force-be-with-you");
```
---

## Problem
### Combine an Array into a String Using the join Method
The join method is used to join the elements of an array together to create a string. It takes an argument for the delimiter that is used to separate the array elements in the string.

Here's an example:
```
var arr = ["Hello", "World"];
var str = arr.join(" ");
// Sets str to "Hello World"
```
Use the join method (among others) inside the sentensify function to make a sentence from the words in the string str. The function should return a string. For example, "I-like-Star-Wars" would be converted to "I like Star Wars". For this challenge, do not use the replace method.
