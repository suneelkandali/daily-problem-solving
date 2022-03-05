**Problem**
Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

 

Example 1:
```js
Input: x = 123
Output: 321
```

Example 2:
```js
Input: x = -123
Output: -321
```
Example 3:
```js
Input: x = 120
Output: 21
```

Constraints:
```js
-231 <= x <= 231 - 1
```

**Solution:**
```js
const reverse = (x) => {
    let output = parseInt(x.toString().split('').reverse().join(''));
    
    if( x < 0) {
        output *= -1;
    }
    
    const range = Math.pow(2, 31);
    const minRange = -1 * range;
    const maxRange = range - 1; 
    
    return output > minRange && output < maxRange ? output : 0;
};
```