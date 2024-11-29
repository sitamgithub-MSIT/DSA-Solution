# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n*2)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def longestPalindrome(self, s: str) -> str:
        """
        Finds the longest palindromic substring in a given string.

        Args:
            s (str): The input string.

        Returns:
            str: The longest palindromic substring.
        """
        def expand_around_center(left: int, right: int) -> str:
            # Expand the window as long as the characters match
            while left >= 0 and right < len(s) and s[left] == s[right]:
                left -= 1
                right += 1

            # Return the palindrome found
            return s[left + 1:right]

        # Initialize the longest palindrome found
        longest = ""
        for i in range(len(s)):
            # Odd-length palindrome (centered at i)
            odd_palindrome = expand_around_center(i, i)

            # Even-length palindrome (centered between i and i+1)
            even_palindrome = expand_around_center(i, i + 1)

            # Update the longest palindrome if a longer one is found
            longest = max(longest, odd_palindrome, even_palindrome, key=len)

        # Return the longest palindrome found
        return longest
```
