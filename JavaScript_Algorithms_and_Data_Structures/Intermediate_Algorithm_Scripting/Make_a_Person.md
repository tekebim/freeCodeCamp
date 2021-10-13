Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Make a Person

Fill in the object constructor with the following methods below:

getFirstName()
getLastName()
getFullName()
setFirstName(first)
setLastName(last)
setFullName(firstAndLast)

Run the tests to see the expected output for each method. The methods that take an argument must accept only one argument and it has to be a string. These methods must be the only available means of interacting with the object.
```

## Solution 1

```javascript
var Person = function (firstAndLast) {
  // Only change code below this line
  // Complete the method below and implement the others similarly     
  this.getFullName = function () {
    return firstAndLast;
  };

  this.getFirstName = function () {
    return firstAndLast.split(" ")[0];
  }

  this.getLastName = function () {
    return firstAndLast.split(" ")[1];
  }

  this.setFirstName = function (first) {
    return firstAndLast = first + " " + this.getLastName();
  }

  this.setLastName = function (last) {
    return firstAndLast = this.getFirstName() + " " + last;
  }

  this.setFullName = function (newFirstAndLast) {
    return firstAndLast = newFirstAndLast;
  }

  return firstAndLast;
};

var bob = new Person('Bob Ross');
```
