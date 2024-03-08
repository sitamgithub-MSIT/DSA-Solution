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
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        """
        Returns the k most frequent elements in the given list of numbers.

        Args:
            nums (List[int]): The list of numbers.
            k (int): The number of most frequent elements to return.

        Returns:
            List[int]: The k most frequent elements.

        """

        # Count the frequency of each number
        count = Counter(nums)

        # Create a heap to store the k most frequent elements
        heap = []
        res = [] # Store the k most frequent elements

        # Add the frequency and number to the heap
        for n in set(nums):
            heap.append(( -count[n], n))

        heapq.heapify(heap)

        # While heap is not empty and k > 0
        while heap and k > 0:

            # Pop the element from the heap and append it to the result
            ele = heapq.heappop(heap)[1]
            res.append(ele)

            # Decrease k by 1
            k -= 1

        # Return the result
        return res
```
