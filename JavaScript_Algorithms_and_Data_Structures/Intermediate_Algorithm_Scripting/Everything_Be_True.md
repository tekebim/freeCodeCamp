Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Everything Be True
Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

In other words, you are given an array collection of objects. The predicate pre will be an object property and you need to return true if its value is truthy. Otherwise, return false.

In JavaScript, truthy values are values that translate to true when evaluated in a Boolean context.

Remember, you can access object properties through either dot notation or [] notation.
```

## Solution 1

```javascript
function truthCheck(collection, pre) {
  let errorsCount = 0;

  collection.map(element => {
    let prop = element[pre];

    if (element.hasOwnProperty(pre)) {
      let errorsException = [undefined, 0, "", null]

      errorsException.map(error => {
        if (prop === error) {
          errorsCount += 1;
        }
      })

      if (typeof (prop) === "number" && isNaN(prop)) {
        errorsCount += 1;
      }
    } else {
      errorsCount += 1;
    }
  })

  return errorsCount === 0;
}

let test = truthCheck([{"single": "yes"}], "single")
```

## Solution 2

```javascript
function truthCheck(collection, pre) {
  var errorsCount = [];

  collection.map(element => {
    if (!element[pre]) {
      errorsCount.push(element);
    }
  })

  return errorsCount.length === 0;
}

let test = truthCheck([{"single": "yes"}], "single");
```
