## twoSum

#### Description

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

#### Examples

`twoSum([2, 7, 11, 15], 9) // [0, 1]`<br>
`twoSum([2, 3, 3, 20], 6) // [1, 2]`

#### Constraints

Time Complexity: O(N)

#### Solution

```js
// solution 1
function twoSum(nums, target) {
  for (var i = 0; i < nums.length; i++) {
    for (var j = i + 1; j < nums.length; j++) {
      if (nums[i] + nums[j] === target) {
        return [i, j];
      }
    }
  }
}
// solution 2 (better run time)
function twoSum(nums, target) {
  var num1;
  var num2;
  let numsHash = new Map(nums.map((elem, i) => [elem, i]));
  for (var i = 0; i < nums.length; i++) {
    num1 = nums[i];
    num2 = target - nums[i];
    if (numsHash.has(num2) && numsHash.get(num2) !== i) {
      return [i, numsHash.get(num2)];
    }
  }
}
```

##### Tags

`#hash-table` `#easy`
