# Counting Sort
### Introduction
Counting Sort is non-comparison sorting algorithm that sorts the elements of an array by counting the number of occurences of each distinct element. Counting sort can only be used to sort elements with non-negative integer keys.

### Complexity
- Time: O(n + k) <br/>
If range is given, we iterate the input array twice. First iteration happens when initializing the count array. Second iteration happens when building the output array. Each iteration has O(n) running time. Calcuating the prefixSum of count has O(k) running time. So the overall time complexity of counting sort is O(n + k).

- Space: O(n + k) <br/>
count array holds up to k distinct values, and output array holds n elements. So the total space complexity is O(n + k).

### C# implementation
```C#
using System.Linq;

public class Solution
{
    public int[] CountingSort(int[] nums)
    {
        // Find range of the array. k is the upper boundary (maximum value) of the range.
        int k = nums.Max();

        // Count the number occurence of each distinct element.
        // Index i is the element's value.
        int[] count = new int[k + 1];
        for (int i = 0; i < nums.Length; i++)
            count[nums[i]]++;

        // Calculate prefix sum on count array
        // count[i] denotes the total number of elements that have value <= i.
        for (int i = 1; i < count.Length; i++)
            count[i] += count[i - 1];

        // Build output array
        // (1) Starting from the end of the original input array, find corresponding index in count for each element.
        // (2) count[i] represents the position of value i. So count[i] - 1 is the index of value i.
        int[] output = new int[nums.Length];
        for(int i = nums.Length - 1; i >= 0; i--)
            output[--count[nums[i]]] = nums[i];

        return output;
    }

    public static void Main(string[] args)
    {
        Solution sol = new Solution();
        int[] arr = new int[] { 5, 9, 3, 1, 3, 4, 1, 0, 2 };
        int[] output = sol.CountingSort(arr);
    }
}
```
