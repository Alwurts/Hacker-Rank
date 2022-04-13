# Hacker Rank - Sales by Match
My solution to the Sales by Match

---

Challenge
--
There is a large pile of socks that must be paired by color. Given an array of integers representing the color of each sock, determine how many pairs of socks with matching colors there are.

Solution 
-----
Loop thourgh the whole array and check if the color is present on a Map object to get quick access time 

Code
---

```js
function sockMerchant(n, ar) {
    let colorMap = new Map();
    
    ar.forEach((value)=>{
        let elementCheck = colorMap.get(value);
        if (elementCheck === undefined){
            colorMap.set(value,1)
        } else if (elementCheck >= 1){
            colorMap.set(value,elementCheck + 1)
        }
    })
    let totalCount = 0;
    for (const [key, count] of colorMap.entries()) {
        totalCount += Math.floor(count / 2)
    }
    return totalCount
}

```

Space time complexity
------
The solution I made will have:

- Time Complexity: O(n)
  - Our worst offender is the loop that goes through the array that holds the object and that is O(n)
- Space Complexity: O(n)
  - Since we are using a map our complexity grows with the size of the array
