# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(N * M)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        """
        Returns the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

        Args:
            - haystack (str): A string.
            - needle (str): A string.

        Returns:
            int: The index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.
        """
        # Iterating through the haystack string
        for i in range(len(haystack)-len(needle)+1):

            # Checking if the current substring that we are observing in haystack is similar to needle or not
            if haystack[i:i+len(needle)] == needle:

                # If similar then return the starting index
                return i
        else:
            # Else return it is absent so return -1
            return -1
```
