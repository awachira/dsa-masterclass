# Asymptotic Analysis: Big-Oh

Asymptotic analysis, more frequently called big-Oh, is an attempt at estimating the resource consumption of an algorithm, hence giving algorithm designers a tool for estimating whether a proposed solution is likely to meet the resource constraints for a problem before implementing an actual program.
It's more of an estimation technique and says nothing about the relative merits of two programs where ones is "slightly faster" than the other.

The most important factor affecting running time is the size of input, `n`, therefore we express the time `T` to run the algorithm as a function of `n`, denoted, `T(n)` where `T(n) > 0`.

The growth rate for an algorithm is the rate at which the cost of the algorithm grows as the size of input grows.
[insert table of growth rates here]


Big-Oh was used as early as 1894 by the number theorist Paul Bachmann. Consider the following snippet:
```c++
void snippet(){
  for(int i = 0; i < n; i++)
    a[i] = i;
}
```
One execution of the method involves:
 - `int i = 0`: one (1) assignment
 - `i < n`    : `n+1` comparisons
 - `i++`      : `n` increments
 - `a[i]`     : `n` array offset computations
 - `a[i] = i` : `n` indirect assignments
 
So the running time of the snippet is
`T(n) = a + b(n+1) + cn + dn + en`
where `a,b,c,d` and `e` are constants that depend on the machine running the code and map to the operations given respectively. The run-time in big-Oh of the above function is simplified to `T(n)= O(n)`, which gives as much information as the previous expression yet is more compact!

Big-Oh allows us to reason at a much higher level, thus making it tractable to analyse more complicated forms.

### Best, Average and Worst Case
These are input sensitive concepts. We consider sequential search algorithm on an array of integers to define them:

#### Best case

This is when the integer we want to find is the first one in the array. Is only useful if the integer has a high probability of occurrence.

#### Worst case 

Happens when the integer we want to find is the last one in the array. It tells us that at least the algorithm performs that well (important for real-time applications).

#### Average case 

Happens when we empirically examine `n/2` values for many inputs of size `n` to find the integer. Important when we wish to aggregate the cost of running the program many times on many different inputs, i.e. it is a statement of the typical behaviour of the algorithm on inputs of size `n`.

### Time Bounds

We survey several terms that describe the running-time equations for an algorithm with reference to some class of inputs of size `n`.

#### Upper bound 

Indicates the upper or highest growth rate achievable by an algorithm. This is synonymous with big-Oh.

#### Lower bound

Used to describe the least amount of resource that an algorithm needs for some class of input. This is big-Omega.

#### big-Theta

This is when the upper and lower bounds are the same within a constant factor.

## Questions

### Qn 1
Write a function that gives the product of 2 numbers using only summation. What is it's run-time?

### Qn 2
Write a function that prints the powers of 3 from 1 through `n` (inclusive):
 - a) Recursively ; b) Without recursive
 - What is the run-time of both (a) and (b) above?
 - (Bonus) Show the call stack in i(a) for `function(125)`
 
### Qn 3
The Fibonacci sequence is given as `1,1,2,3,5,...` where a number in the sequence is the sum of the two previous numbers starting with the base sequence `1,1`. Write a function that computes the sequence
 - a) Recursively ; b) non-recursively
 - What are the space complexities for both implementations above?
 - What are the time complexities for both implementations above?
 - You can improve the run time by `'memoising'` previously computed values: do this 
   for both implementations. What is the runtime after doing so?
   
### Qn 4
Write a function that computes `n!` recursively and non-recursively.
 - What is its time and space complexity for both implementations?
 - Memoise the implementations and report on the time and space complexities.
 
### Qn 5 
Write a function that checks if a number is prime.
 - What is the function's time and space complexity?
 - Implement it using memoisation: What is the resulting time and space complexity?
 
### *Qn 6 
Write a function that computes the sum of values in a balanced binary search tree
 - a) recursively ; b) non-recursively
 - What are the time and space complexities of both implementations above?
 
### Qn 7
Discuss the run-time concepts, best case, worst case and expected (average) case in the context of:
 - any search algorithm
 - any sort algorithm

## References
- Open Data structures
- Dempster Shaffer: