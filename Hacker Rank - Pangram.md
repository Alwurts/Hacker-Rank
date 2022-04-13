# Hacker Rank - Pangrams
My solution to the Pangrams

---

Challenge
--
A pangram is a string that contains every letter of the alphabet. Given a sentence determine whether it is a pangram in the English alphabet. Ignore case. Return either pangram or not pangram as appropriate.

Solution 
-----



Code
---

```js
function pangrams(s) {
    console.log("s: " + s)
    let alphabetMap = new Map();
    //let noSpaceS = s.trim(" ");
    //console.log("noSpaceS: " + noSpaceS)
    for (let i = 0; i < s.length; i++){
        
        let elementCharLower = s[i].toLowerCase(); // Case doesnt count so lower it
        let elementCheck = alphabetMap.get(elementCharLower); // Check if we have seen the character already
        
        if (elementCheck === undefined){
            
            alphabetMap.set(elementCharLower,1)
            
        } else if (elementCheck >= 1){
            
            alphabetMap.set(elementCharLower,elementCheck + 1)
            
        }
        
    }

    let panagram = true;
    
    // Check map against a(ASCII 97) through c(ASCII 122)
    for (let i = 97; i <= 122; i++){
        
        let check = alphabetMap.get(String.fromCharCode(i));
        
        if (alphabetMap.get(String.fromCharCode(i)) === undefined){
            
            panagram = false
            break;
            
        } 
        
    }
    
    if (panagram){
        
        return ("pangram")
        
    } else {
        
        return ('not pangram')
        
    }

}
```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n + k) - reduces to O(n)
  - n is length of the string we receive
  - k is the length of the alphabet 
- Space Complexity: O(n)
  - We are using a hash table so our space will grow as the length of the string grows
 