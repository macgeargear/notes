## ex.8
> suppose we had an algorithm that took in an array of strings, sorted each string, and then sorted the full array. What would the runtime be?

firstly, i think sorted each string in array use `O(nlogn)` and sort entire array use `O(mlogm)` may be the answer is `O(nlogn + mlogm)` but is was completely incorrect!.

let's define new terms-and use names that ar logical
- let `s` be the length of the longest string.
- let `a` be the length of the array 

Now we can work through this in parts:
- sorting each string is `O(slogs)`
- we have to do this for every string so that's `O(a*slogs)`
- now we have to sort all the strings. firstly, i also think it just `O(aloga)`. but it wrong again!!
- to sort you have to compare each string that's `O(s)`. There are `O(aloga)` comparisons, therefore this will take `O(s*aloga)` 

**In summary**
- sorting each string: `O(a*slogs)`
- compare and sorting array: `O(s*aloga)`
so the time complexity is `O(as*(loga+logs))`
