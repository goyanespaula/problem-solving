## seperatePositive

#### Description

Write a function called separatePositive which accepts an array of non-zero integers. Separate the positive integers to the left and the negative integers to the right. The positive numbers and negative numbers need not be in sorted order.

#### Examples

`separatePositive([2, -1, -3, 6, -8, 10]) // [2, 10, 6, -3, -1, -8]` <br>
`separatePositive([5, 10, -15, 20, 25]) // [5, 10, 25, 20, -15]` <br>
`separatePositive([-5, 5]) // [5, -5]` <br>
`separatePositive([1, 2, 3]) // [1, 2, 3]` <br>

#### Constraints

Time Complexity: O(N)
Space Complexity: O(1)

#### Solution

```js
function separatePositive(arr, i = 0, j = arr.length - 1) {
  if (i >= j) {
    return arr;
  }
  if (arr[i] > 0) {
    i++;
  } else if (arr[j] < 0) {
    j--;
  } else {
    [arr[i], arr[j]] = [arr[j], arr[i]];
    i++;
    j--;
  }
  return separatePositive(arr, i, j);
}
```

##### Tags

`#swap` `#easy` `#recursion` `#tail-recursion`
