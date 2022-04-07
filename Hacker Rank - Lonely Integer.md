# Hacker Rank - Lonely Integer
My solution to the Lonely Integer

---

Challenge
--
Given an array of integers, where all elements but one occur twice, find the unique element.

Solution #1 Non Performant
-----

This solution has a nested for loop where it checks each element against the whole array which is very inneficient but works

Code
---

```js
function lonelyinteger(a) {
    let unique = true;
    
    for (let i = 0; i < a.length; i++){
        for (let j = 0; j < a.length; j++){
            if (a[i] === a[j] && i !== j){
                unique = false;
                console.log("Not unique")
            }
        }
        if (unique){
            console.log("Returning value: " + a[i])
            return a[i]
        }
        
        unique = true;
    }

}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n)
  - This time im using a Map object which has constant time access, I do have two array that equal in time complexity to O(2n) which then gets simplified to O(n)
- Space Complexity: O(n)
  - Since we are using a hashmap our space complexity will grow as we add more items to the array
 
Solution #2 More-ish Performant
-----

This solution uses a Map object which has an access time of O(1) instead of a nested loop

Code
---

```js
function lonelyinteger(a) {

    let mapObject = new Map();
   
    for (let i = 0; i < a.length; i++){
        let elementCheck = mapObject.get(a[i]);
        if (elementCheck === undefined){
            mapObject.set(a[i],1)
        } else if (elementCheck >= 1){
            mapObject.set(a[i],elementCheck + 1)
        }
        
    }
    console.log("Not getting here")
    for (const [key, value] of mapObject.entries()) {
        console.log("Nevermind: " + key + " : " + value)
        if(value === 1){
            console.log(key)
            return key
        }
    }
}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n2)
  - Since we have a nested loop but the array is the same we can use power of 2 to represent worst time
- Space Complexity: O(1)
  - Each space can be reused in the next loop


