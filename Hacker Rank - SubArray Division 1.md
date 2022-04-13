# Hacker Rank - SubArray Division 1
My solution to the SubArray Division 1

---

Challenge
--
Two children, Lily and Ron, want to share a chocolate bar. Each of the squares has an integer on it.

Lily decides to share a contiguous segment of the bar selected such that:

- The length of the segment matches Ron's birth month, and,
- The sum of the integers on the squares is equal to his birth day.

Determine how many ways she can divide the chocolate.

Solutionish #1
-----
Loop through the whole array and compare against a nested loop of the size of blocks you want to get


Code
---

```js
function birthday(s, d, m) {
    // Write your code here
    console.log("Squares: " + s)
    console.log("Day: " + d)
    console.log("Month: " + m)
    let numberWays = 0;
    let segmentCount;
    for (let i = 0; i <= (s.length - m); i++){
        segmentCount = 0
        for (let j = 0; j < m; j++){
            segmentCount += s[i + j];
            console.log("i: " + i, ",j: " + j)
        }
        if (segmentCount == d){
            numberWays++;
        }
    }
    return numberWays
}
```

Space time complexity
------
The solution I made will have:

- Time Complexity: O(nm)
  - Where n is the size of the array that holds the numbers and m is the size of the block you are looking for
- Space Complexity: O(1)
  - Since space is reutilized with each loop
