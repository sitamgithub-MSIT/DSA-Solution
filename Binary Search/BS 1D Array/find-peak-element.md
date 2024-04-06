# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
class Solution:
    def findPeakElement(self, nums: List[int]) -> int:
        """
        Finds the peak element in a given 1D array using binary search.

        Args:
            nums (List[int]): The input array of integers.

        Returns:
            int: The index of the peak element in the array.
        """

        # If the array is empty, return 0
        if not nums:
            return 0

        # If the array has only one element, return 0
        if len(nums) == 1:
            return 0

        # Initialize low and high
        low, high = 0, len(nums) - 1

        # While low is less than high
        while(low < high):

            # Calculate mid
            mid = (low + high)//2

            # If the mid element is greater than the next element, set high to mid
            if nums[mid] > nums[mid + 1]:
                high = mid

            # If the mid element is less than the next element, set low to mid + 1
            elif nums[mid] < nums[mid + 1]:
                low = mid + 1

        # Return the high element
        return high
```
