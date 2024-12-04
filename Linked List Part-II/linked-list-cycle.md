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
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        """
        Determines if a linked list has a cycle.

        Args:
            head (Optional[ListNode]): The head of the linked list.

        Returns:
            bool: True if the linked list has a cycle, False otherwise.
        """
        # Initialize the slow and fast pointers
        slow, fast = head, head

        # Move the fast pointer twice as fast as the slow pointer
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

            # If there is a cycle, return True
            if slow == fast:
                return True

        # If there is no cycle, return False
        return False
```
