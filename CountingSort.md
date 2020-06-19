# Counting Sort
### Introduction
Counting Sort is non-comparison sorting algorithm that sorts the elements of an array by counting the number of occurences of each distinct element. Counting sort can only be used to sort elements with non-negative integer keys.

### Alogrithm
1. Find the range (max value) of the input unsorted array.
2. Count the number of occurrence of each distinct element.
3. Count prefix sum (cumulative sum) on count array.
4. Build output array.

### Complexity
- Time: O(n + k) <br/>
If range is given, we iterate the input array twice. First iteration happens when initializing the count array. Second iteration happens when building the output array. Each iteration has O(n) running time. Calcuating the prefixSum of count has O(k) running time. So the overall time complexity of counting sort is O(n + k).

- Space: O(n + k) <br/>
count array holds up to k distinct values, and output array holds n elements. So the total space complexity is O(n + k).

### Pros and Cons
- Pros:
1. Counting sort runs in linear time complexity.

- Cons:
1. Restricted inputs: counting sort only works for sorting non-negative elements.
2. Space cost: counting sort has O(n) space complexity. If the range of the input array is big, then a lot of space is needed.

### C# implementation
```C#
using System.Linq;

public class Solution
{
    public int[] CountingSort(int[] nums)
    {
        int[] output = new int[nums.Length];

        // step1: find the max value of the input unsorted array
        int max = nums.Max();

        // step2: count the number of occurrence of each distinct element
        // index of count is the element.
        int[] count = new int[max + 1];
        foreach(int n in nums)
            count[n]++;

        // step3: calculate prefix sum on count
        // count[i] denotes there are count[i] elements have value <= i
        for (int i = 1; i < count.Length; i++)
            count[i] += count[i - 1];

        // step4: build output array
        // - starting from the end of input array to ensure stable sorting result
        // - count[nums[i]] represents nums[i]'s last position. 
        //   So count[nums[i]] - 1 is nums[i]'s index in the sorted output array.
        for (int i = nums.Length - 1; i >=0; i--)
        {
            output[count[nums[i]] - 1] = nums[i];
            count[nums[i]]--;
        }

        return output;
    }

    static void Main(string[] args)
    {
        Solution sol = new Solution();
        int[] nums = new int[] { 5, 9, 3, 1, 3, 4, 1, 0, 2 };
        int[] output = sol.CountingSort(nums);
    }
}
```
