## minIndexSum

#### Description

Credit[https://leetcode.com/problems/minimum-index-sum-of-two-lists/description/](LeetCode)
Suppose Andy and Doris want to choose a restaurant for dinner, and they both have a list of favorite restaurants represented by strings.

You need to help them find out their common interest with the least list index sum. If there is a choice tie between answers, output all of them with no order requirement. You could assume there always exists an answer.

#### Examples

`minIndexSum(["Shogun", "Tapioca Express", "Burger King", "KFC"],["Piatti", "The Grill at Torrey Pines", "Hungry Hunter Steakhouse", "Shogun"]) // ["Shogun"]`<br>
`minIndexSum(["Taco Bell", "Tapioca Express", "Burger King", "KFC"],["KFC", "Taco Bell", "Burger King"]) // ["Taco Bell]`<br>
`minIndexSum(["Taco Bell", "Burger King", "KFC"],["KFC", "Zaxby's", "Taco Bell"]) // ["KFC", "Taco Bell"]`

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
