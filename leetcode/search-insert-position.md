**Problem**
Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.


**Examples**
Example 1:
```js
Input: nums = [1,3,5,6], target = 5
Output: 2
```

Example 2:
```js
Input: nums = [1,3,5,6], target = 2
Output: 1
```

Example 3:
```js
Input: nums = [1,3,5,6], target = 7
Output: 4
```


**Constraints:**
1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums contains distinct values sorted in ascending order.
-104 <= target <= 104


**Approach:**
  - At first checking if targeted number if less than first index or greater than last Index.
  - Then we can apply Binary Search Algorithm
  - If not found it will be greater than last Index


**Solution**
```js
var searchInsert = function(nums, target) {
  if (target < nums[0]) return 0
  else if (target > nums[nums.length - 1]) return nums.length

  let start = 0;
  let end = nums.length - 1;

  while (start <= end) {
    const mid = parseInt((start + end)/2);
    const guess = nums[mid];

    if (guess === target) {
      return mid;
    }
    else if (guess > target) {
      end = mid - 1;
    }
    else {
      start = mid + 1;
    }
  }
  
  return start;

};
```
