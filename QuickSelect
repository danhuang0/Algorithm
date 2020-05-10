#Quick Select
Quick select is a selection algorithm to select Kth smallest or largest element in an unordered list. I was invented by Tony Hoare.

```
public class Solution
{
    public int FindKthLargest(int[] nums, int k)
    {
        int resIdx = nums.Length - k;
        int left = 0, right = nums.Length - 1;

        while (left < right)
        {
            int pivLoc = Partition(nums, left, right);

            if (resIdx == pivLoc)
                break;
            else if (resIdx < pivLoc)
                right = pivLoc - 1;
            else
                left = pivLoc + 1;
        }

        return nums[resIdx];
    }

    /// <summary>
    /// divide nums into two parts. 
    /// Elements less than the pivot will be on the left part.
    /// Elements greater than the pivot will be on the right part.
    /// </summary>
    /// <param name="nums"></param>
    /// <param name="left"></param>
    /// <param name="right"></param>
    /// <returns>index of pivot</returns>
    private int Partition(int[] nums, int left, int right)
    {
        int pivot = nums[right];
        int pivLoc = left;

        for (int i = left; i < right; i++)
        {
            if (nums[i] <= pivot)
            {
                Swap(nums, i, pivLoc);
                pivLoc++;
            }
        }

        Swap(nums, pivLoc, right);

        return pivLoc;
    }

    private void Swap(int[] nums, int i, int j)
    {
        int tmp = nums[i];
        nums[i] = nums[j];
        nums[j] = tmp;
    }
}
```
