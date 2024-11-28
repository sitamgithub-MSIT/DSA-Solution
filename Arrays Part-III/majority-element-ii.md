# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(n)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```python3 []
class Solution:
    def majorityElement(self, nums: List[int]) -> List[int]:
        """
        Finds all elements in the input list that appear more than n/3 times,
        where n is the length of the list.

        Args:
            nums (List[int]): The input list of integers.

        Returns:
            List[int]: A list containing the majority elements that appear more than n/3 times.
        """
        # Initialize count1, count2, ele1, and ele2 to 0 and None
        count1, count2 = 0, 0
        ele1, ele2 = None, None

        # Iterate through the list of integers
        for n in (nums):
            # If the current element is equal to ele1, increment count1
            if ele1 == n:
                count1 += 1

            # If the current element is equal to ele2, increment count2
            elif ele2 == n:
                count2 += 1

            # If count1 is 0, set ele1 to the current element
            elif count1 == 0:
                ele1 = n
                count1 += 1

            # If count2 is 0, set ele2 to the current element
            elif count2 == 0:
                ele2 = n
                count2 += 1

            # Otherwise, decrement count1 and count2
            else:
                count1 -= 1
                count2 -= 1

        # Return the majority elements
        return[x for x in(ele1,ele2) if nums.count(x)>len(nums)//3]
```
