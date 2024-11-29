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
    def findKthLargest(self, nums: List[int], k: int) -> int:
        """
        Finds the kth largest element in an array using a max heap.

        Args:
            - nums (List[int]): The input array of integers.
            - k (int): The position of the largest element to find.

        Returns:
            int: The kth largest element in the array.
        """
        # Initializing our heap with numbers present in nums but converting each to negative to implement the max heap
        heap = [-n for n in nums]

        # Heapify the heap that we had previously created
        heapq.heapify(heap)

        # While heap is not empty and k > 1
        while heap and k > 1:

            # Pop element from heap
            heapq.heappop(heap)

            # Updating k by decreasing 1 each time
            k -= 1

        # The top will contain the Kth largest element but before returning we have to make it positive
        return -heap[0]
```
