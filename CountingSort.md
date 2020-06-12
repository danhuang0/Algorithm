```C#
using System.Linq;

public class Solution
{
    /*
     * Time: O(n + k)
       If range is given, we iterate the input array twice. First iteration happens when initializing the count array.
       Second iteration happens when building the output array. Calcuating the prefixSum of count needs O(k) operation.

     * Space：O(n + k)
       count array holds up to k distinct values, and output array holds n elements. So the total space complexity is O(n + k).
     */
    public int[] CountingSort(int[] nums)
    {

        // Find range of the array. k is the upper boundary of the range.
        int k = nums.Max();

        // Count occurence of each distinct element. Use index to represent elements.
        int[] count = new int[k + 1];
        for (int i = 0; i < nums.Length; i++)
            count[nums[i]]++;

        // count[i]: the number of elements whose value is less than/equal to value i.
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
