# Radix Sort
### Introduction
Radix Sort is non-comparative sorting algorithm. It avoids comparision by creating and distributing elements into buckets according to their radix. Radix sort distributes elements starts from the lowest significant digit (LSD) to the most significant digit (MSD), thus radix sort is also called bucket sort and digit sort.

### Alogrithm
Sort input array by using counting sort from least significant digit (LSD) to most significant digit (MSD).

### Complexity
- Time: O(d*(n + b)) <br/>
Time complexity for counting sort is O(n + b) where n is the size of input array, b is the base/radix for representing numbers. Radix sort will use counting sort d times where d is the number of digit of the max value.

- Space: O(n + b) <br/>
count array holds up to b distinct values, and output array holds n elements. So the total space complexity is O(n + b).

### References
1. https://en.wikipedia.org/wiki/Radix_sort
2. https://www.geeksforgeeks.org/radix-sort
3. https://en.wikipedia.org/wiki/Radix

### C# implementation
```C#
using System.Linq;

public class Solution
{
    public void RadixSort(int[] nums)
    {
        int max = nums.Max();

        // power = 10^i where i is the current digit
        // sort elements starts from the least significant digit (LSD) to most significant digit (MSD)
        for (int power = 1; max / power > 0; power *= 10)
            CountingSort(nums, power);
    }

    public void CountingSort(int[] nums, int power)
    {
        int[] output = new int[nums.Length];
        int[] count = new int[10];

        // (n / power) % 10 maps current digit to count's index
        foreach (int n in nums)
            count[(n / power) % 10]++;

        for (int i = 1; i < count.Length; i++)
            count[i] += count[i - 1];

        for(int i = nums.Length - 1; i >= 0; i--)
        {
            output[count[(nums[i] / power) % 10] - 1] = nums[i];
            count[(nums[i] / power) % 10]--;
        }

        for (int i = 0; i < nums.Length; i++)
            nums[i] = output[i];
    }

    static void Main(string[] args)
    {
        Solution sol = new Solution();
        int[] nums = new int[] { 15, 9, 103, 1, 50, 49};
        sol.RadixSort(nums);
    }
}
```
