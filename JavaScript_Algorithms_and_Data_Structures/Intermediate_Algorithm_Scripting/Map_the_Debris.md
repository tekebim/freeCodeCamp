Created by Michael R. Year : 2021 - 13/10/2021 Personal learning courses

```
Map the Debris
Return a new array that transforms the elements' average altitude into their orbital periods (in seconds).

The array will contain objects in the format {name: 'name', avgAlt: avgAlt}.

You can read about orbital periods on Wikipedia.

The values should be rounded to the nearest whole number. The body being orbited is Earth.

The radius of the earth is 6367.4447 kilometers, and the GM value of earth is 398600.4418 km3s-2.
```

## Solution 1

```javascript
function orbitalPeriod(arr) {
  let elements = Array.from(arr);

  function getOrbitalPeriod(avgAlt) {
    const GM = 398600.4418;
    const earthRadius = 6367.4447;
    const a = avgAlt + earthRadius;
    return Math.round((2 * Math.PI) * Math.sqrt(Math.pow(a, 3) / GM));
  }

  elements.map(element => {
    element['orbitalPeriod'] = getOrbitalPeriod(element['avgAlt'])
    delete element['avgAlt'];
  })

  return elements;

}

let result = orbitalPeriod([{name: "iss", avgAlt: 413.6}, {name: "hubble", avgAlt: 556.7}, {
  name: "moon",
  avgAlt: 378632.553
}]);
```
