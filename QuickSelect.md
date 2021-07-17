## Introduction
Quickselect is a selection algorithm to find the Kth smallest/largest element in an unsorted list. Quickselect uses the same overall approach as Quicksort, choosing one element as the pivot and then partition the elements in two parts: numbers smaller than the pivot are in the first group, numbers greater than or equal to the pivot are in the second group. Unlike Quicksort, Quickselect only recurses into one side that has the element it is searching for. 

## Complexity
Like Quicksort, Quickselect is fast in practice but has poor worst-case performance. The worst-case time complexity is O(n^2), the average and best case time complexity is O(n).

* Worst-case
Each partitioning only excludes one elements, so the time complexity is n + (n-1) + (n-2) + ... + 2 + 1 = n*(n+1)/2, which is O(n^2).
* Average case
Each partitioning excludes half of all the elements, so the time complexity is n + n/2 + n/4 + ... + 1 = 2n*[1-(1/2)^n] < 2n, which is O(n).

## Implementation
```C#
public class Solution {
    public int FindKthLargest(int[] nums, int k) {
        
        int left = 0, right = nums.Length - 1;
        int expectedIdx = nums.Length - k;
        
        while(left <= right)
        {
            int pivotLoc = Partition(nums, left, right);
            
            if(pivotLoc == expectedIdx)
                return nums[expectedIdx];
            else if(pivotLoc < expectedIdx)
                left = pivotLoc + 1;
            else
                right = pivotLoc - 1;
        }
        
        return Int32.MinValue;
    }
    
    private int Partition(int[] nums, int left, int right)
    {
        int pivot = nums[right];
        int pivotLoc = left;
        for(int i = left; i < right; i++)
        {
            if(nums[i] < pivot)
            {
                Swap(nums, i, pivotLoc);
                pivotLoc++;
            }
        }
        
        Swap(nums, pivotLoc, right);
        
        return pivotLoc;
    }
    
    private void Swap(int[] nums, int i, int j)
    {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```
