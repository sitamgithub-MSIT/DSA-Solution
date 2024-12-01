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
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        """
        Finds all unique triplets in the given array that sum up to zero.

        Args:
            nums (List[int]): The input array of integers.

        Returns:
            List[List[int]]: A list of lists containing the unique triplets that sum up to zero.
        """

        # First sort the nums array
        nums.sort()

        # Array to store our result
        res = []

        # Running through the nums array
        for i in range(len(nums)):

            # checking if any duplicate we counter. If it is then continue
            if i > 0 and nums[i] == nums[i-1]:
                continue

            # Applying two sum approach
            l, r = i+1, len(nums)-1

            # Loop condition
            while(l < r):

                two_sum = nums[l] + nums[r]
                three_sum = nums[i] + nums[l] + nums[r]

                # If taget_sum greater than zero then update the right pointer
                if three_sum > 0:
                    r -= 1

                # If taget_sum lesser than zero then update the left pointer
                elif three_sum < 0:
                    l += 1

                # If we got the triplets then append it to the res array
                else:
                    res.append([nums[i],nums[l],nums[r]])
                    l += 1

                    # To avoid duplicates
                    while(nums[l] == nums[l-1] and l < r):
                        l += 1

        # Return the res array
        return res
```
