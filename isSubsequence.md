## seperatePositive

#### Description

Write a function called isSubsequence which takes in two strings and checks whether the characters in the first string form a subsequence of the characters in the second string. In other words, the function should check whether the characters in the first string appear somewhere in the second string, without their order changing.

#### Examples

`isSubsequence('hello', 'hello world'); // true` <br>
`isSubsequence('sing', 'sting'); // true` <br>
`isSubsequence('abc', 'abracadabra'); // true` <br>
`isSubsequence('abc', 'acb'); // false`

#### Constraints

Time Complexity - O(N + M)
Space Complexity - O(1)

#### Solution

```js
function isSubsequence(substr, str) {
  var j = 0;
  if (substr.length === 0) return true;
  for (var i = 0; i < str.length; i++) {
    if (str[i] === substr[j]) {
      j++;
      if (j === substr.length) return true;
    }
  }
  return false;
}
```

##### Tags

`#easy` `#two-pointer`
