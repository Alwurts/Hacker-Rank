# Hacker Rank - Permuting two arrays
My solution to the Pangrams

---

Challenge
--
There are two -element arrays of integers,  and . Permute them into some  and  such that the relation  holds for all  where .

There will be  queries consisting of , , and . For each query, return YES if some permutation ,  satisfying the relation exists. Otherwise, return NO.

Solutionish #1
-----
This works for all but one case of hackerank


Code
---

```js
function twoArrays(k, A, B) {
    console.log(A + " : " + B)
    let sum = 0;
    for(let i = 0; i < A.length; i++){
        sum += A[i] + B[i]
    }
    
    if ((sum / A.length) >= k){
        return "YES"
    } else {
        return "NO"
    }
}
```

Space time complexity
------
The solution I made will have:
