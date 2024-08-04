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
    def isAnagram(self, s: str, t: str) -> bool:
        """
        Determines if two strings are anagrams of each other.

        Args:
            s (str): A string.
            t (str): A string.

        Returns:
            bool: True if the strings are anagrams of each other, False otherwise.
        """

        # Count the frequency of each character in both strings
        count1 = Counter(s)
        count2 = Counter(t)

        # If the lengths of the strings are different, they cannot be anagrams
        if(len(s) != len(t)):
            return False

        # Iterate through the characters in the second string
        for i in t:

            # If the character is present in the first string
            if count1[i] > 0:
                # If the frequency of the character is greater in the second string
                if count1[i] < count2[i]:
                    return False

            # If the character is not present in the first string
            else:
                return False

        # The strings are anagrams, return True
        return True
```
