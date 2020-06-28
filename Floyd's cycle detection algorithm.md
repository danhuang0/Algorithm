# Floyd's cycle detection algorithm

Floyd's cycle detection algorithm (a.k.a tortoise and hare algorithm) can be used to find cycle within a LinkedList, or a sequence of iterated function values, or a finite-state machine.

## Alogrithm
- Define two pointers: slow and fast. They both point at the start position initially.
- Move slow pointer by one and fast pointer by two every time. If slow pointer and faster poiner meet, then there is cycle. Otherwise, there is no cycle.
- Reset fast pointer to the start position, then move slow pointer and fast pointer by one every time, eventually they will meet at the entry of the cycle.

## LinkedList


## Iterated function values



## References
1. https://en.wikipedia.org/wiki/Cycle_detection
2. https://en.wikipedia.org/wiki/Iterated_function
