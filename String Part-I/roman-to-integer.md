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
    def romanToInt(self, s: str) -> int:
        """
        Converts a Roman numeral string to an integer.

        Args:
            s (str): The Roman numeral string to convert.

        Returns:
            int: The integer representation of the Roman numeral.
        """
        # Create a dictionary to store the values of each Roman numeral
        dic = {"I": 1, "V": 5, "X": 10, "L": 50, "C": 100, "D": 500, "M": 1000}

        # Initialize the answer to 0
        ans = 0

        # Iterate through the string
        for i in range(len(s)):

            # If the current numeral is smaller than the next numeral, subtract its value
            if i + 1 < len(s) and dic[s[i]] < dic[s[i + 1]]:
                ans -= dic[s[i]]

            # Otherwise, add its value
            else:
                ans += dic[s[i]]

        # Return the answer
        return ans
```
