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
    def lengthOfLongestSubstring(self, s: str) -> int:

        # Initialize the left pointer, the set and the result
        string_set = set()
        l = 0
        res = 0

        # Iterate through the string
        for r in range(len(s)):

            # While the current character is in the set
            while s[r] in string_set:

                # Remove the left character from the set and update the left pointer
                string_set.remove(s[l])
                l += 1

            # Add the current character to the set and update the result
            string_set.add(s[r])
            res = max(res, r-l+1)

        # Return the result
        return res
        
```
