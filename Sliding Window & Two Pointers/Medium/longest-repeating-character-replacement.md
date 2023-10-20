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
    def characterReplacement(self, s: str, k: int) -> int:

        # Initialize the left pointer, the dictionary and the result
        l = 0
        dic = {}
        res = 0

        # Iterate through the string 
        for r in range(len(s)):

            # Update the dictionary with the current character and its count
            dic[s[r]] = 1 + dic.get(s[r], 0)

            # While the difference between the length of the window and the max value in the dictionary is greater than k 
            while(r-l+1) - max(dic.values()) > k:
                
                # Update the dictionary removing the left character and the left pointer 
                dic[s[l]] -= 1
                l += 1

            # Update the result 
            res = max(res, r-l+1)

        # Return the result
        return res
        
```
