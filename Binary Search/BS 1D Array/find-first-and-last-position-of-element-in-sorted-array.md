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
    def searchRange(self, nums: List[int], target: int) -> List[int]:
        """
        Finds the first and last position of the target value in a sorted array.

        Args:
            nums (List[int]): The sorted array of integers.
            target (int): The target value to search for.

        Returns:
            List[int]: A list containing the first and last position of the target value in the array.
        """

        # Find the left and right indices of the target value
        left = self.binarysearch(nums,target,True)
        right = self.binarysearch(nums,target,False)
        return([left,right])


    def binarysearch(self,nums,target,leftbias):
        """
        Performs binary search to find the position of the target value in the array.

        Args:
            nums (List[int]): The sorted array of integers.
            target (int): The target value to search for.
            leftbias (bool): A flag indicating whether to bias the search towards the left or right side of the array.

        Returns:
            int: The position of the target value in the array. Returns -1 if the target value is not found.
        """

        # Initialize the left and right pointers
        l, r = 0, len(nums)-1
        i = -1

        # Loop condition
        while(l <= r):

            # Calculate the mid
            mid = (l + r)//2

            # If the mid value is greater than the target value, update the right pointer
            if(nums[mid] > target):
                r = mid - 1

            # If the mid value is lesser than the target value, update the left pointer
            elif(nums[mid] < target):
                l = mid + 1

            # If the mid value is equal to the target value
            else:
                i = mid

                # Bias the search towards the left side of the array
                if leftbias:
                    r = mid - 1

                # Bias the search towards the right side of the array
                else:
                    l = mid + 1

        # Return the position of the target value
        return(i)
```
