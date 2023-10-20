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
    def longestOnes(self, nums: List[int], k: int) -> int:

        # Initialize the left pointer, the result
        l=0
        res=0

        # Iterate through the array
        for r in range(len(nums)):

            # If the current number is 0
            if nums[r]==0:

                # If k is 0
                if k==0:

                    # Update the left pointer until it reaches one
                    while nums[l]!=0:
                        l+=1
                    l+=1
                
                # If k is not 0
                else:
                    k-=1

            # Update the result
            res=max(res,r-l+1)

        # Return the result
        return res
    
```
