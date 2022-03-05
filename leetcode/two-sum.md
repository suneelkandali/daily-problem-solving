# Two Sum

### Understanding the problem

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:
```js
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

Example 2:
```js
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

Example 3:
```js
Input: nums = [3,3], target = 6
Output: [0,1]
```

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.


## Solution:
```js
const twoSum = (nums, target) => {
    const prevValues = {};
    for (let i = 0; i < nums.length; i++) {
        let currentValue = nums[i];
        let requiredValue = target - currentValue;
        let index2 = prevValues[requiredValue];
        
        if (index2 != null) {
            return [index2, i];
        } else {
            prevValues[currentValue] = i;
        }
    }
    return [];
};
```
