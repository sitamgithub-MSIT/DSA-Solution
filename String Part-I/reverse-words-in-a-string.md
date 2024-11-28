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
    def reverseWords(self, s: str) -> str:
        """
        Reverses the order of words in a given string.

        Args:
            s (str): The input string.

        Returns:
            str: The input string with the order of words reversed.
        """
        # Split the string into words and reverse the list
        s = s.split()
        s.reverse()

        # Return the reversed string
        return(" ".join(s))
```
