Given a string s, find the length of the longest substring without repeating characters.

Example 1:
```js
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

Example 2:
```js
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

Example 3:
```js
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "kew", with the length of 3.
```
 

Constraints:

0 <= s.length <= 5 * 104
s consists of English letters, digits, symbols and spaces.

Approach:
 

Solution:
```js
const lengthOfLongestSubstring = (s) => {
    let count = 0;

    let i = 0; // For tracking first Index
    let j = 0; // For tracking last Index
    let n = s.length;

    let set = new Set();

    while (i < n && j < n) {
        let char = s.charAt(j);
        if(!set.has(char)) {
            set.add(char);
            j++;
            count = Math.max (count, j - i);
        } else {
            set.delete(s.charAt(i));
            i++;
        }
    }

    return count;
};

const result = lengthOfLongestSubstring('abcabcbb');
console.log(result);
```
