# Hacker Rank - Mini-Max Sum
My solution to the Mini-Max Sum

---

Challenge
--
Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.

Solution #1
-----
My solution consist on sorting the array we receive, and then loop through the sorted array and for:
- Minimum sum we add the first 4 values (1-4)
- Maxiumum sum we add the last 4 values (2-5)

Code
---

```js
function miniMaxSum(arr) {
    let maximumSum = 0;
    let minimumSum = 0;
    
    arr.sort(function(a, b){return a - b})
    
    arr.slice().forEach((value, index)=>{
        //console.log(index)
        if (index > 0){maximumSum += value}
        if (index < 4){minimumSum += value}
    })
    console.log(minimumSum + " " + maximumSum)
}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n log n)
  - The arr.protoype.sort() function uses a different algorithm depending on the browser but overall they use merge sort which has O(n log n) time complexity.
  - The forEach loop through the array has a time complexity of O(n), since the time complexity of the merge sort is worst, then we use that
- Space Complexity: O(n)
  - For every new item of the array our space complexity would grow linear to its size.
  - Merge sort has a space complexity of O(n), and the looping through the array has a space complexity of O(n) so we use the one for the merge sort

Solution #2
----

Give that the array size is 5 and that the we want to sum 4 values we can do the following:

- Minimum sum = <sum of all values> - <maximum value in the array>
- Maxiumum sum = <sum of all values> - <minimum value in the array>

Code
----
```js
function miniMaxSum(arr) {
    let sum = 0;
    let minVal = arr[0];
    let maxVal = arr[0];

    arr.slice().forEach((value)=>{
        //console.log(index)
        sum += value
        if (value < minVal){minVal = value}
        if (value > maxVal){maxVal = value}
    })
    console.log((sum - maxVal) + " " + (sum - minVal))
}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n)
  - Since we are only looping through the array once our time complexity grows linearly with the length of the array.
- Space Complexity: O(1)
  - Looping through an array only uses O(1) since space can be reused on each iteration.