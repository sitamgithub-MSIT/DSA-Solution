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
    def search(self, nums: List[int], target: int) -> int:
        """
        Binary search algorithm to find the index of a target value in a sorted 1D array.

        Args:
            nums (List[int]): The sorted array of integers.
            target (int): The value to search for in the array.

        Returns:
            int: The index of the target value in the array, or -1 if it is not found.
        """

        # Initializing low and high pointer for nums array
        low, high = 0, len(nums)-1

        # While the following condition holds run the loop
        while(low <= high):

            # Calculating mid
            mid = (low + high)//2

            # If target value is greater than the mid value then update the low pointer as (low = mid + 1)
            if nums[mid] < target:
                low = mid + 1

            # If target value is lesser than the mid value then update the high pointer as (high = mid - 1)
            elif nums[mid] > target:
                high = mid - 1

            # Else the element is found and return the index where the target value is present
            else:
                return mid

        # Even after terminating the loop if the target element is not found then it means that the desired element is not in the array. So, return -1
        return -1
```
