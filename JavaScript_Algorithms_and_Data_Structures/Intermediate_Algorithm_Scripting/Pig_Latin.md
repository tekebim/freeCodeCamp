Created by Michael R. Year : 2021 - 06/10/2021 Personal learning courses

```
Pig Latin is a way of altering English Words. The rules are as follows:

- If a word begins with a consonant, take the first consonant or consonant cluster, move it to the end of the word, and add ay to it.

- If a word begins with a vowel, just add way at the end.

Translate the provided string to Pig Latin. Input strings are guaranteed to be English words in all lowercase.
```

## My solution 1

```javascript
function translatePigLatin(str) {
  const vowelsRegex = '^[aAeEiIoOuU].*';
  const isStartingWithVowels = str.match(vowelsRegex);
  let word;

  if (isStartingWithVowels) {
    const suffix = "way";
    word = str + suffix;
  } else {
    let firstConsonants = [str.charAt(0)]
    const suffix = "ay";
    let consonantsLetters = str.match('[a-z][^aAeEiIoOuU]*');
    let rest = str.substring(consonantsLetters[0].length);
    word = rest + consonantsLetters + suffix;
  }
  return word;
}
```

## My solution 2

```javascript
function translatePigLatin(str) {
  const vowels = ['a', 'e', 'i', 'o', 'u'];

  function isVowel(letter) {
    return vowels.indexOf(letter);
  }

  for (let i = 0; i < str.length; i++) {
    let individualLetter = str[i];
    if (isVowel(individualLetter) !== -1) {
      if (i === 0) {
        return str + "way";
      } else {
        return str.slice(i) + str.slice(0, i) + "ay";
      }
    }
  }
  return str + "ay";
}

translatePigLatin("california");
```
