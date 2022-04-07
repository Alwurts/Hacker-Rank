# Hacker Rank - Time Conversion
My solution to the Time Conversion

---

Challenge
--
Given a time in -hour AM/PM format, convert it to military (24-hour) time.
Note: 
- 12:00:00AM on a 12-hour clock is 00:00:00 on a 24-hour clock.
- 12:00:00PM on a 12-hour clock is 12:00:00 on a 24-hour clock.

Solution
-----
My solution consist on ...

Code
---

```js
function timeConversion(s) {
    console.log(s.slice(-2))
    if (s.slice(-2) === "AM"){
        if (s.slice(0,2) === "12"){
            return ("00" + s.slice(2,s.length - 2))
        } else {
            return s.slice(0,s.length - 2)
        }
        
    } else {
        if (s.slice(0,2) === "12"){
            return s.slice(0,s.length - 2)
        } else {
            let newPm = parseInt(s.slice(0,2)) + 12
            return (newPm + s.slice(2,s.length - 2))
        } 
    }
}

```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n)
  - The arr.protoype.slice() has a time complexity of O(n)
  - If staments have O(1)
- Space Complexity: O(n)
  - For every new item of the array our space complexity would grow linear to its size.
  - Merge sort has a space complexity of O(n), and the looping through the array has a space complexity of O(n) so we use the one for the merge sort

