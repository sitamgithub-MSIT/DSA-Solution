# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        """
        Finds the maximum sum of a subarray within the given list of integers.

        Args:
            nums (List[int]): The list of integers.

        Returns:
            int: The maximum sum of a subarray.
        """
        # Initialize local_max and global_max to the first element of the list
        local_max = nums[0]
        global_max = nums[0]

        # Iterate through the list of integers
        for i in range(1, len(nums)):

            # Update local_max to the maximum of the current element and the sum of the current element and local_max
            local_max = max(nums[i], nums[i] + local_max)

            # Update global_max to the maximum of local_max and global_max
            if local_max > global_max:
                global_max = local_max

        # Return the global maximum
        return global_max
```
