## longestFall

#### Description

Write a function called longestFall, which accepts an array of integers, and returns the length of the longest consecutive decrease of integers.

#### Examples

`longestFall([5, 3, 1, 3, 0]) // 3, 5-3-1 is the longest consecutive sequence of decreasing integers` <br>
`longestFall([2, 2, 1]) // 2, 2-1 is the longest consecutive sequence of decreasing integers` <br>
`longestFall([2, 2, 2]) // 1, 2 is the longest consecutive sequence of decreasing integers` <br>
`longestFall([5, 4, 4, 4, 3, 2]) // 3, 4-3-2 is the longest` <br>
`longestFall([9, 8, 7, 6, 5, 6, 4, 2, 1]) // 5, 9-8-7-6-5 is the longest` <br>
`longestFall([]) // 0` <br>

#### Solution

```js
function longestFall(arr) {
  let tempCount = 1;
  let longest = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > arr[i + 1]) {
      tempCount++;
    } else {
      if (tempCount > longest) {
        longest = tempCount;
      }
      tempCount = 1;
    }
  }
  return longest;
}
```

##### Tags

`#sliding-window` `#easy`
