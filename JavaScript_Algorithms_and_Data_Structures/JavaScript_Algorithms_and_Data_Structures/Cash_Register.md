Created by Michael R. Year : 2021 - 16/10/2021 Personal learning courses

```
Cash Register
Design a cash register drawer function checkCashRegister() that accepts purchase price as the first argument (price), payment as the second argument (cash), and cash-in-drawer (cid) as the third argument.

cid is a 2D array listing available currency.

The checkCashRegister() function should always return an object with a status key and a change key.

Return {status: "INSUFFICIENT_FUNDS", change: []} if cash-in-drawer is less than the change due, or if you cannot return the exact change.

Return {status: "CLOSED", change: [...]} with cash-in-drawer as the value for the key change if it is equal to the change due.

Otherwise, return {status: "OPEN", change: [...]}, with the change due in coins and bills, sorted in highest to lowest order, as the value of the change key.
```

```
Currency Unit	Amount
Penny	$0.01 (PENNY)
Nickel	$0.05 (NICKEL)
Dime	$0.1 (DIME)
Quarter	$0.25 (QUARTER)
Dollar	$1 (ONE)
Five Dollars	$5 (FIVE)
Ten Dollars	$10 (TEN)
Twenty Dollars	$20 (TWENTY)
One-hundred Dollars	$100 (ONE HUNDRED)
```

`See below for an example of a cash-in-drawer array:`

```
[
  ["PENNY", 1.01],
  ["NICKEL", 2.05],
  ["DIME", 3.1],
  ["QUARTER", 4.25],
  ["ONE", 90],
  ["FIVE", 55],
  ["TEN", 20],
  ["TWENTY", 60],
  ["ONE HUNDRED", 100]
]
```

## Solution 1

```javascript
function checkCashRegister(price, cash, cid) {
  // Update currencies base to be easier manipulated 
  let currencies = {
    "PENNY": 1,
    "NICKEL": 5,
    "DIME": 10,
    "QUARTER": 25,
    "ONE": 100,
    "FIVE": 500,
    "TEN": 1000,
    "TWENTY": 2000,
    "ONE HUNDRED": 10000
  }

  let amountRest = Math.round(cash * 100) - Math.round(price * 100);
  let result = {
    status: "",
    change: []
  }
  let changeDue = {};
  let virtualAmountCapacity = {};

  cid.reverse().map(value => {
    let cidCurrencyName = value[0];
    let cidActualCapacity = Math.round(value[1] * 100);

    while (amountRest >= currencies[cidCurrencyName] && cidActualCapacity !== 0) {
      if (changeDue[cidCurrencyName] !== undefined) {
        changeDue[cidCurrencyName] += currencies[cidCurrencyName];
      } else {
        changeDue[cidCurrencyName] = currencies[cidCurrencyName];
      }
      amountRest -= currencies[cidCurrencyName]
      cidActualCapacity -= currencies[cidCurrencyName]
    }
    virtualAmountCapacity[cidCurrencyName] = cidActualCapacity
  })

  if (amountRest > 0) {
    result.status = "INSUFFICIENT_FUNDS"
    return result
  }
  
  // Check if all virtualAmount are empty
  if (Object.entries(virtualAmountCapacity).every(entry => entry[1] === 0)) {
    result.status = "CLOSED"
    result.change = [...cid].reverse()
    return result
  }
  
    let changeArray = []
    Object.entries(changeDue).map(entry => {
      changeArray.push([entry[0], entry[1] / 100])
    })
    result.status = "OPEN"
    result.change = changeArray;
    return result;
}

checkCashRegister(19.5, 20, [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])
```
