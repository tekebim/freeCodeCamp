Created by Michael R. Year : 2021 - 14/10/2021 Personal learning courses

```
Roman Numeral Converter
Convert the given number into a roman numeral.

All roman numerals answers should be provided in upper-case.
```

## Solution 1 (after refactoring)

````javascript
function convertToRoman(num) {
  let romanNumeral = "";
  let pairValues = {
    3000: "MMM",
    2000: "MM",
    1100: "MC",
    1000: "M",
    900: "CM",
    800: "DCCC",
    700: "DCC",
    600: "DC",
    500: "D",
    400: "CD",
    300: "CCC",
    200: "CC",
    100: "C",
    90: "XC",
    80: "LXXX",
    70: "LXX",
    60: "LX",
    50: "L",
    40: "XL",
    30: "XXX",
    20: "XX",
    10: "X",
    9: "IX",
    5: "V",
    4: "IV",
    1: "I"
  }

  Object.entries(pairValues).reverse().map(value => {
    while (num >= value[0]) {
      romanNumeral += value[1];
      num -= value[0];
    }
  });

  return romanNumeral;
}

convertToRoman(2014);
````

## Solution 2

```javascript
function convertToRoman(num) {
  let romanNumeral = "";

  let values = {
    3000: "MMM",
    2000: "MM",
    1100: "MC",
    1000: "M",
    900: "CM",
    800: "DCCC",
    700: "DCC",
    600: "DC",
    500: "D",
    400: "CD",
    300: "CCC",
    200: "CC",
    100: "C",
    90: "XC",
    80: "LXXX",
    70: "LXX",
    60: "LX",
    50: "L",
    40: "XL",
    30: "XXX",
    20: "XX",
    10: "X",
  }

  while (num > 0) {
    Object.entries(values).reverse().map(value => {
      if (num >= value[0]) {
        romanNumeral += value[1];
        num -= value[0];
      }
    });

    if (num === 9) {
      romanNumeral += "IX";
      num -= 9;
    } else if (num >= 5) {
      romanNumeral += "V";
      num -= 5;
    } else if (num < 4 && num > 0) {
      romanNumeral += "I";
      num -= 1;
    } else if (num === 4) {
      romanNumeral += "IV";
      num -= 4;
    }
  }

  return romanNumeral;
}

convertToRoman(2014);
```
