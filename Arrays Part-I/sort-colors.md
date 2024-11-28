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
    def sortColors(self, nums: List[int]) -> None:
        """
        Sorts an array of integers containing only 0s, 1s, and 2s in-place.

        Args:
            nums (List[int]): The array of integers to be sorted.

        Returns: None
        """
        # Initialize low, mid, and high pointers to 0, 0, and the length of the array minus 1
        low, mid, high = 0, 0, len(nums)-1

        # While mid is less than or equal to high
        while(mid <= high):

            # If the element at mid is 0, swap it with the element at low and increment low and mid
            if(nums[mid] == 0):
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1

            # Else if the element at mid is 1, increment mid
            elif(nums[mid] == 1):
                mid += 1

            # Else swap the element at mid with the element at high and decrement high
            else:
                nums[high], nums[mid] = nums[mid], nums[high]
                high -= 1
```
