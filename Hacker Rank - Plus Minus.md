# Hacker Rank - Plus Minus
My solution to the Plus Minus Problem

---

Challenge
--
Given an array of integers, calculate the ratios of its elements that are positive, negative, and zero. Print the decimal value of each fraction on a new line with  places after the decimal.

Solution
-----
My solution is written in JavaScript and simply loops through the array and checks if the value is positive, negaive or zero and counts them.

At the end of the loop we get the ratios by dividing <count of numbers> / <array length> 

Code
---

```js
function plusMinus(arr) {
    // Write your code here
    
    let positive = 0;
    let negative = 0;
    let zero = 0;
    
    arr.forEach((val)=>{
        if (val > 0){
            positive++;
        } else if (val === 0) {
            zero++;
        } else {
            negative++;
        }
    })
    
    console.log(positive / arr.length )
    console.log(negative  / arr.length )
    console.log(zero / arr.length )
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n)
  - Because we have to loop through the whole array to see all values, therefore as the array grows, the time grows linearly
- Space Complexity: O(1)
  - Because each iteration of our loop through the array ocupies O(1) space, but the same space can be used for the next iteration

