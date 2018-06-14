## sameFrequency

#### Description

Write a function called separatePositive which accepts an array of non-zero integers. Separate the positive integers to the left and the negative integers to the right. The positive numbers and negative numbers need not be in sorted order.

#### Examples

`sameFrequency(182,281) // true`<br>
`sameFrequency(34,14) // false` <br>
`sameFrequency(3589578, 5879385) // true` <br>
`sameFrequency(22,222) // false`

#### Constraints

Time Complexity: O(N)

#### Solution

```js
function sameFrequency(num1, num2) {
  var num1Arr = num1.toString().split("");
  var num2Arr = num2.toString().split("");
  if (num1Arr.length !== num2Arr.length) return false;
  var freqCount = num1Arr.reduce((accum, curr) => {
    accum[curr] = (accum[curr] || 0) + 1;
    return accum;
  }, {});
  for (var n of num2Arr) {
    if (!freqCount[n] || freqCount[n] === 0) {
      return false;
    } else {
      freqCount[n]--;
    }
  }
  return true;
}
```

##### Tags

`#frequency-counter` `#easy`
