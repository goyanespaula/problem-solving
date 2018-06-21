## findLongestSubstring

#### Description

Write a function called findLongestSubstring, which accepts a string and returns the length of the longest substring with all distinct characters.

#### Examples

`findLongestSubstring('')` // 0 <br>
`findLongestSubstring('rithmschool')` // 7 <br>
`findLongestSubstring('thisisawesome')` // 6 <br>
`findLongestSubstring('thecatinthehat')` // 7 <br>
`findLongestSubstring('bbbbbb')` // 1 <br>
`findLongestSubstring('longestsubstring')` // 8 <br>
`findLongestSubstring('thisishowwedoit')` // 6

#### Constraints

Time Complexity: O(N)

#### Solution

```js
function findLongestSubstring(str) {
  var i = 0;
  var j = 1;
  var maxCount = 0;
  var tempSeen = { [str[0]]: 0 };
  if (str.length === 0) return 0;
  while (j < str.length) {
    if (tempSeen.hasOwnProperty(str[j])) {
      maxCount = Math.max(j - i, maxCount);
      i = tempSeen[str[j]] + 1;
      j = i + 1;
      tempSeen = { [str[i]]: i };
    } else {
      tempSeen[str[j]] = j;
      j++;
    }
  }
  return Math.max(j - i, maxCount);
}
```

##### Tags

`#two-pointer` `#medium`
