# Hacker Rank - Max Min
My solution to the Max Min

---

Challenge
--
You will be given a list of integers, , and a single integer . You must create an array of length  from elements of  such that its unfairness is minimized. Call that array . Unfairness of an array is calculated as

Where:
- max denotes the largest integer in 
- min denotes the smallest integer in 



Solution 
-----
1. First order the array
2. Loop through the array starting at index = k 
3. Substract our current index - (index - k)


Code
---

```js
function maxMin(k, arr) {
    
    console.log(arr)
    
    arr.sort(function(a, b){return a - b}) // Merge sort so O(n log n)
    
    let minValue = Infinity
    
    for(let i = k - 1; i < arr.length; i++){ // O(n-k)
        let tempUnfairness = arr[i]-arr[i-k+1]
        if (tempUnfairness < minValue){
            minValue = tempUnfairness
        }
    }
    
    console.log(arr)
    console.log(minValue)
    return minValue
    
}
```

Space time complexity
------
The solution I made will have:

- Time Complexity: O(n log n)
  - Since we are sorting the arr with arr.Sort() which uses merge sort 
- Space Complexity: O(n)
  - Time complexity of merge sort 
