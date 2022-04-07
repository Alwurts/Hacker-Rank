# Hacker Rank - Sparse Arrays
My solution to the Sparse Arrays

---

Challenge
--
There is a collection of input strings and a collection of query strings. For each query string, determine how many times it occurs in the list of input strings. Return an array of the results.

Solution #1 Non Performant
-----

Times out on HackerRank

Code
---

```js
function matchingStrings(strings, queries) {

    let queriesResults = [];
    
    queries.forEach((valueQuery, indexQuery)=>{
        queriesResults.push(0);
        strings.forEach((valueString, indexString)=>{
  
            if (valueString === valueQuery){
                queriesResults[queriesResults.length - 1]++; 
            }
        })
    })

    return queriesResults

}

```

Space time complexity
------
The solution I made will have:
- Time Complexity: O(n * m)
  - There are 2 different arrays and 1 forEach loop for every array, each for loop is O(n) and O(m) respectively, but combined you multiply them
- Space Complexity: ?

