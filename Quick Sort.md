## Introduction
QuickSort is a divide-and-conquer alogrithm that is developed by British computer scientist Tony Hoare in 1959. It is a comparision sorting alogrithm.


## Alogrithm
1. Pick pivot element
2. Partitioning: Split the array into two parts such that elements with value less than the pivot locate in the first half, elements with value greater than the pivot locate in the second half.
3. Recursively apply step 1 and 2 to two sub-arrays.


## Complexity Analysis
In worst case, each pivot index we get for the next round of split is at the end of the arrays, then QuickSort has O(N^2) time complexity. The algorithm needs to iterate N elements at the 1st round, then iterate (N - 1) elements at the 2nd round, then iterate (N - 2) elements at the 3rd round, and so on.

In average, each pivot index split the array into two sub-arrays have the same lengths, so the depth of split is logN. At each depth, the algorithm will iterate N elements, so the time complexity is O(NlogN).


## Implementation
```C#
public class Solution {
    public int[] SortArray(int[] nums) {
        
        QuickSort(nums, 0, nums.Length - 1);
        return nums;
    }
    
    private void QuickSort(int[] nums, int left, int right)
    {        
        if(left < right)
        {
            int pivotIndex = Partition(nums, left, right);
            QuickSort(nums, left, pivotIndex - 1);
            QuickSort(nums, pivotIndex + 1, right);
        } 
    }
    
    private int Partition(int[] nums, int left, int right)
    {
        int pivot = nums[right];
        int pivotIndex = left;
        
        for(int i = left; i < right; i++)
        {
            if(nums[i] <= pivot)
            {
                Swap(nums, i, pivotIndex);
                pivotIndex++;
            }
        }
        
        Swap(nums, pivotIndex, right);
        return pivotIndex;
    }
    
    private void Swap(int[] nums, int i, int j)
    {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```

#### References
1. https://en.wikipedia.org/wiki/Quicksort
