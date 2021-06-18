# Prefix Sum

## Introduction
Prefix sum is also known as cumulative sum or inclusive sum. 

For an one-dimensional array ```arr[]``` of size n, its prefix sum array ```prefixSum[]``` will have size of n, and ```prefixSum[i] = arr[0] + arr[1] + ... + arr[i]```.

For an two-dimensional array ```arr[][]```,
- if ```i = 0 && j = 0```, then ```preSum[0][0] = arr[0][0]```
- if ```i = 0```, then ```preSum[0][j] = preSum[0][j-1] + arr[0][j]```
- if ```j = 0```, then ```preSum[i][0] = preSum[i-1][0] + arr[i][0]```
- if ```j != 0 && i != 0```, then```preSum[i][j] = preSum[i-1][j] + preSum[i][j-1] + src[i][j] - preSum[i-1][j-1]```


## Problems

## References
- https://en.wikipedia.org/wiki/Prefix_sum
- https://www.geeksforgeeks.org/prefix-sum-array-implementation-applications-competitive-programming/
- https://juejin.cn/post/6944913393627168798
- https://www.cs.cmu.edu/~guyb/papers/Ble93.pdf
