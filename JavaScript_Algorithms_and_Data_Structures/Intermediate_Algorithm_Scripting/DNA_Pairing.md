Created by Michael R. Year : 2021 - 12/10/2021 Personal learning courses

```
The DNA strand is missing the pairing element. Take each character, get its pair, and return the results as a 2d array.

Base pairs are a pair of AT and CG. Match the missing element to the provided character.

Return the provided character as the first element in each array.

For example, for the input GCG, return [["G", "C"], ["C","G"], ["G", "C"]]

The character and its pair are paired up in an array, and all the arrays are grouped into one encapsulating array.
```

## My solution 1

```javascript
function pairElement(str) {
  const arrayPair = {
    'A': 'T',
    'T': 'A',
    'C': 'G',
    'G': 'C'
  }

  let resultArray = [];

  for (let i = 0; i < str.length; i++) {
    Object.entries(arrayPair).map(entry => {
      if (str[i] === entry[0]) {
        resultArray.push([entry[0], entry[1]])
      }
    });
  }

  return resultArray;
}
```

## Solution 2

````javascript

function calculatePair(initial) {
  if (initial === "A") {
    return "T";
  } else if (initial === "T") {
    return "A"
  } else if (initial === "C") {
    return "G"
  } else if (initial === "G") {
    return "C"
  }
}

function pairElement(str) {
  return str.split("").map(initialPair => {
    let pair = [initialPair, calculatePair(initialPair)]
    return pair;
  })
}
````
