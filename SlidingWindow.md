# Sliding Window

## Introduction
Sliding window algorithm can be used to solve problems that require checking some parts of data that is organized in linear data structures such as Array, String, LinkedList, etc. As the name suggests, sliding window alogrithm forms a window over some parts of data and the window will slide over the data to capature different portions of it. 


## How to identify sliding window problems
- The problems will involve a data structure that is ordered and iterable like an array, a string or a linked list.
- The problems often ask for contigous and optimal things, like the longest sequence or shortest sequence of something that satisfies a given condition exactly.


## Benefits of using sliding window
The sliding window problems usually can also be solved by brute force solutions which will run in O(N^2), O(2^N) or some other large time complexity. This is because brute force solutions will validate all the possible solutions, and this will cause duplicated work. For example, visit the same element multiple times. By using sliding window algorithm, we can visit each element only once, so that achieve the linear time complexity.


## Sliding window problems are dynamic programming problems
Sliding window problems are a subset of dynamic programming problems because
- Overrlapping: The subproblems are overlapping.
- Optimal Substructure: The overall optimal solution can be obtained by using optimal solutions of its subproblems.

## Fixed-size sliding window

## Flexible-SIze sliding window
[209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

## Reference
1. https://medium.com/outco/how-to-solve-sliding-window-problems-28d67601a66
2. https://levelup.gitconnected.com/an-introduction-to-sliding-window-algorithms-5533c4fe1cc7
3. https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/?ref=lbp
4. https://www.geeksforgeeks.org/optimal-substructure-property-in-dynamic-programming-dp-2/
5. https://www.youtube.com/watch?v=MK-NZ4hN7rs
