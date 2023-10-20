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
    def numberOfSubstrings(self, s: str) -> int:

        # Initialize the left pointer, the dictionary and the result
        l = 0
        dic = {}
        res = 0

        # Iterate through the string
        for r in range(len(s)):

            # Update the dictionary with the current character and its count
            dic[s[r]] = 1 + dic.get(s[r], 0)

            # While the dictionary has all three characters
            while len(dic) == 3:

                # Update the result and the dictionary removing the left character
                res += len(s) - r
                dic[s[l]] -= 1

                # If the count of the left character is 0, remove it from the dictionary
                if dic[s[l]] == 0:
                    dic.pop(s[l])

                # Update the left pointer
                l += 1

        # Return the result
        return res
        
```
