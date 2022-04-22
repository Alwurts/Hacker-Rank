# Hacker Rank - Caesars Cipher
My solution to the Caesars Cipher

---

Challenge
--
Julius Caesar protected his confidential information by encrypting it using a cipher. Caesar's cipher shifts each letter by a number of letters. If the shift takes you past the end of the alphabet, just rotate back to the front of the alphabet. In the case of a rotation by 3, w, x, y and z would map to z, a, b and c.

Original alphabet:      abcdefghijklmnopqrstuvwxyz
Alphabet rotated +3:    defghijklmnopqrstuvwxyzabc

Solution 
-----
My solution is very simple in that it check if its Uppercase or lowercase in order to bound the ascii values that we will later use.
Inside a loop we check what the ascii value is and add k characters to it, if it goes over z or Z then loop back to A
Code
---

```js
function caesarCipher(s, k) {
    // Write your code here
    
    // Y = 102 + 98 = 200
    // 200 > 90 YES
    // 96 + (200 - 122)
    let newString = ""
    s.split('').forEach((each)=>{
        let charAscii = each.charCodeAt(0);
        if (charAscii >= 65 && charAscii <= 90){
            let newAscii = charAscii + k;
            if (newAscii > 90){
                newAscii = 64 + ((newAscii - 90) % 26)
                if (newAscii == 64){
                    newAscii = 90;
                }
                
            }
            newString += (String.fromCharCode(newAscii))
        } else if (charAscii >= 97 && charAscii <= 122){
            let newAscii = charAscii + k;
            if (newAscii > 122){
                
                newAscii = 96 + ((newAscii - 122) % 26)
                if (newAscii == 96){
                    newAscii = 122;
                }
            }
            newString += (String.fromCharCode(newAscii))
        } else {
            newString += each
        }
    })
    return(newString)
}

```

Space time complexity
------
The solution I made will have:

- Time Complexity: O(n)
  - Where n is the lenght of the String
- Space Complexity: O(1)
  - We are looping and reusing values so it can be near constant 
