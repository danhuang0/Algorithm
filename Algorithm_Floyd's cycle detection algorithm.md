# Floyd's cycle detection algorithm

Floyd's cycle detection algorithm (a.k.a tortoise and hare algorithm) can be used to check whether there is a cycle within a LinkedList, or a sequence of iterated function values, or a finite-state machine. It can also be used to calculate the entry of the cycle if it exists.


## Alogrithm
- Define two pointers: slow and fast. They both point at the start position initially.
- Move slow pointer by one and fast pointer by two every time. If slow pointer and faster poiner can meet, then there is cycle. Otherwise, there is no cycle.
- Reset fast pointer to the start position, then move slow pointer and fast pointer by one every time, eventually they will meet at the entry of the cycle.

## Alogrithm Proof
![image](https://github.com/idanhuang/DataStructure-and-Algorithm/blob/master/image/floyd's%20cycle%20detection.PNG)

- Assume the distance between start point and cycle entry is m. Distance between cycle point and meet point is k (clockwise).
- When slow pointer and fast pointer meet, the distance that slow pointer goes through is i = m + a * n + k. Since fast pointer moves at twice the speed, then the distance that fast pointer goes through is 2 * i = m + b * n + k.
- So i = (b - a) * n. In other words, when slow pointer and fast pointer meet, the distance that slow pointer goes through is an integer multiple of the cycle length, i.e., i = k * n. Since the distance between start point and cycle entry is m, we will further know m = p. Because m + k = k + p = a full cycle length.

 
## LinkedList
- [141 Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
- [142 Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)

## Iterated function (迭代函数) values
An iterated function is a function which is obtained by composing another function with itself a certain number of times. 迭代函数重复的，与自身复合的函数。


- [202. Happy Number](https://leetcode.com/problems/happy-number/)
- [287. Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)

## References
1. https://en.wikipedia.org/wiki/Cycle_detection
2. https://en.wikipedia.org/wiki/Iterated_function
