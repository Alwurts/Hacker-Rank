# Hacker Rank - Diagonal Difference
My solution to the Diagonal Difference

---

Challenge
--
Given a square matrix, calculate the absolute difference between the sums of its diagonals.

Solution 
-----

The solution has a loop that runs through the lenght of the side of the matrix
Code
---

```js
function diagonalDifference(arr) {

    let sum1 = 0;
    let sum2 = 0;
    
    for (let i = 0; i < arr.length; i++){
        sum1 += arr[i][i]
        sum2 += arr[i][arr[0].length - 1 - i]
    }
    return Math.abs(sum1 - sum2)
    //arr [0][2] + arr[1][1] + arr[2][0]
}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n)
  - The time grows linearly with the number of columns in the matrix
- Space Complexity: O(1)
  - We are reusing space as we loop through the matrix
 