Created by Michael R. Year : 2021 - 13/02/2021 Personal learning courses

```
Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.
```

## My solution 1

```javascript
function convertHTML(str) {

  let htmlSymbolsChar = {
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    "\"": "&quot;",
    "'": "&apos;"
  }

  let strSplitted = str.split("");
  strSplitted.map((letter, index) => {
    Object.entries(htmlSymbolsChar).map(specialChar => {
      if (letter === specialChar[0]) {
        strSplitted[index] = specialChar[1]
      }
    })
  })
  return strSplitted.join("");
}

convertHTML("Dolce & Gabbana");
```
