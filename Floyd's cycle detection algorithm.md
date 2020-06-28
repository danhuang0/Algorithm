# Floyd's cycle detection algorithm

Floyd's cycle detection algorithm (a.k.a tortoise and hare algorithm) can be used to check whether there is a cycle within a LinkedList, or a sequence of iterated function values, or a finite-state machine. It can also be used to calculate the entry of the cycle if it exists.


## Alogrithm
- Define two pointers: slow and fast. They both point at the start position initially.
- Move slow pointer by one and fast pointer by two every time. If slow pointer and faster poiner can meet, then there is cycle. Otherwise, there is no cycle.
- Reset fast pointer to the start position, then move slow pointer and fast pointer by one every time, eventually they will meet at the entry of the cycle.

## Alogrithm Proof
![image](https://github.com/idanhuang/DataStructure-and-Algorithm/blob/master/image/floyd's%20cycle%20detection.PNG)

When slow pointer and fast pointer meet, the distance that slow pointer went through is i = m + a * n + k. <br/>
Since fast pointer moves at twice the speed, then the distanec fast pointer went through is 2 * i = m + b * n + k. <br/> 
So i = (b - a) * n. In other words, when slow pointer and fast pointer meet, the distance that slow pointer went through is an integer multiple of the cycle length (i = k * n). Since the distanec between start point and cycle entry is m , we will further know m = p.

 

## LinkedList


## Iterated function values



## References
1. https://en.wikipedia.org/wiki/Cycle_detection
2. https://en.wikipedia.org/wiki/Iterated_function
