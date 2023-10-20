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
    def totalFruit(self, fruits: List[int]) -> int:

        # Initialize the left pointer, the dictionary and the result
        l = 0
        dic = {}
        res = 0

        # Iterate through the array
        for r in range(len(fruits)):

            # Update the dictionary with the current fruit and its count
            dic[fruits[r]] = 1 + dic.get(fruits[r], 0)

            # While the dictionary has more than 2 types of fruits
            while len(dic) > 2:

                # Update the dictionary removing the left fruit
                dic[fruits[l]] -= 1

                # If the count of the left fruit is 0, remove it from the dictionary
                if dic[fruits[l]] == 0:
                    dic.pop(fruits[l])

                # Update the left pointer
                l += 1

            # Update the result
            res = max(res, r-l+1)

        # Return the result
        return res

```
