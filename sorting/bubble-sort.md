# Bubble Sort

### Understanding the problem

Given an array of integers, we are asked to sort the input array in ascending order using Bubble Sort and return the sorted array.

#

### Approach:

Bubble Sort sort an array by repeatedly iterating through an array and in each pass swapping the adjacent elements if they are in wrong order.

Suppose we have the following array of numbers:

```
[8, 5, 2, 9, 6, 1]
```

We start at index `0`, compare `8` to the number right next to it, which is `5`.

```
[8, 5, 2, 9, 6, 1]
 ^
```

`8` is greater than `5`, we swap these two numbers:

```
[5, 8, 2, 9, 6, 1]
 ^
```

We then move on to index `1`, compare `8` to the number comes after it.

```
[5, 8, 2, 9, 6, 1]
    ^
```

Since `8` is greater than `2`, put them in order:

```
[5, 2, 8, 9, 6, 1]
    ^
```

We move on to index `2`.

```
[5, 2, 8, 9, 6, 1]
       ^
```

`8` is smaller than `9`, they are in correct order, so we move on to index `3`.

```
[5, 2, 8, 9, 6, 1]
          ^
```

`9` is larger than `6`, swap them:

```
[5, 2, 8, 6, 9, 1]
          ^
```

Move on to index `4`.

```
[5, 2, 8, 6, 9, 1]
             ^
```

`9` is greater than `1`, we swap the two numbers:

```
[5, 2, 8, 6, 1, 9]
             ^
```

We can notice that the largest number in the array, which is `9`, is now in the final correct order. The reason for that is whenever we get to the largest number in the array, the number is going to be swapped all the way to the end of the array. And since it is in the final position, we don't need to check it again.

We then start at index `0` again, compare `5` to `2`.

```
[5, 2, 8, 6, 1, 9]
 ^
```

`5` is greater than `2`, so we swap the two numbers.

```
[2, 5, 8, 6, 1, 9]
 ^
```

Move on to index `1`.

```
[2, 5, 8, 6, 1, 9]
    ^
```

`5` is smaller than `8`, we don't need to touch these two numbers and we move on to index `2`, and compare `8` to `6`.

```
[2, 5, 8, 6, 1, 9]
       ^
```

`8` is greater than `6`, we swap these two numbers:

```
[2, 5, 6, 8, 1, 9]
       ^
```

Move on to index `3`.

```
[2, 5, 6, 8, 1, 9]
          ^
```

`8` is larger than `1`, swap them:

```
[2, 5, 6, 1, 8, 9]
          ^
```

Now the second largest element in the array, `8`, is in the final position.

We go all the way back to index `0`, loop through the array again and perform the same logic. We keep doing this until no swaps were made, which indicates the array is sorted.


### Implementation

```js
function bubbleSort(arr){
    // Outer pass
    for(let i = 0; i < arr.length; i++){
        // Inner pass
        for(let j = 0; j < arr.length - i - 1; j++){
            // Value comparison using ascending order
            if(arr[j + 1] < arr[j]){
                //Swapping
                [arr[j + 1],arr[j]] = [arr[j],arr[j + 1]]
            }
        }
    };
    return arr;
};

console.log(bubbleSort([8, 5, 2, 9, 6, 1]));
```

### Complexity Analysis

- Worst-case time complexity: Big O (n^2).

- Average-case time complexity: Big theta (n^2).

- Best-case time complexity: Big omega (n).

- Space complexity: Big O (1).