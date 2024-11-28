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

```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        """
        Finds the longest common prefix string amongst an array of strings.

        Args:
            strs (List[str]): The list of strings.

        Returns:
            str: The longest common prefix string.
        """
        ans = ""    # Initialize the answer

        # Sort the strings
        strs = sorted(strs)

        # Get the first and last strings
        first, last = strs[0], strs[-1]

        # Iterate through the characters of the first and last strings
        for i in range(min(len(first), len(last))):

            # If the characters are not equal, return the answer
            if first[i] != last[i]:
                return ans

            # Otherwise, add the character to the answer
            else:
                ans += first[i]

        # Return the answer
        return ans
```
