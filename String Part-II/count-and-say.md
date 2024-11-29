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

```python3 []
class Solution:
    def countAndSay(self, n: int) -> str:
        """
        Generates the nth term in the "count-and-say" sequence.

        Args:
            n (int): The position of the term in the sequence to generate.

        Returns:
            str: The nth term in the "count-and-say" sequence.
        """
        # Base case for n = 1
        result = "1"

        for _ in range(n - 1):
            # Initialize an empty string and a count variable
            current = ""
            count = 1
            for i in range(1, len(result)):
                # If the current character is the same as the previous one, increment the count
                if result[i] == result[i - 1]:
                    count += 1

                # If the current character is different from the previous one, append the count and the character to the current string
                else:
                    current += str(count) + result[i - 1]
                    count = 1

            # Append the count and the last character to the current string
            current += str(count) + result[-1]
            result = current

        # Return the result
        return result
```
