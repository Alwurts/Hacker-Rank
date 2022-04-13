# Hacker Rank - Counting Sort 1
My solution to the Counting Sort 1

---

Challenge
--
Comparison Sorting
Quicksort usually has a running time of , but is there an algorithm that can sort even faster? In general, this is not possible. Most sorting algorithms are comparison sorts, i.e. they sort a list just by comparing the elements to one another. A comparison sort algorithm cannot beat  (worst-case) running time, since  represents the minimum number of comparisons needed to know where to place each element. For more details, you can see these notes (PDF).

Alternative Sorting
Another sorting method, the counting sort, does not require comparison. Instead, you create an integer array whose index range covers the entire range of values in your array to sort. Each time a value occurs in the original array, you increment the counter at that index. At the end, run through your counting array, printing the value of each non-zero valued index that number of times.

Solution 
-----

Implementing counting sort with arrays

Code
---

```js
function countingSort(arr) {
    let indexTracker = Array(100).fill(0) // CHANGE TO 101
    //console.log(indexTracker)
    for(let i = 0; i < arr.length; i++){
        indexTracker[arr[i]]++;
    }
    
    let orderedArray = []
    
    for(let i = 0; i < indexTracker.length; i++){
        for(let j = 0; j < indexTracker[i]; j++){
            orderedArray.push(i)
        }
    }
    
    console.log(orderedArray) // THE ACTUAL ORDERED ARRAY
    
    return indexTracker
}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n + k)
  - n is number of items to order
  - k is the maximum value that we can find in that array
- Space Complexity: O(n)
  - For each iteration of our loop we need to keep an item in memory
 