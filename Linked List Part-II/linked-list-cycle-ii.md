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
    def detectCycle(self, head: Optional[ListNode]) -> Optional[ListNode]:
        """
        Detects the node where the cycle begins in a linked list, if there is a cycle.

        Args:
            head (Optional[ListNode]): The head of the linked list.

        Returns:
            Optional[ListNode]: The node where the cycle begins, or None if there is no cycle.
        """
        # Initialize slow and fast pointers
        slow, fast = head, head

        # Move the fast pointer twice as fast as the slow pointer
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

            # If there is a cycle, break the loop
            if slow == fast:
                break

        # If there is no cycle, return None
        else:
            return None

        while head != slow:
            # Move the head and slow pointers one step at a time
            head = head.next
            slow = slow.next

        # Return the node where the cycle starts
        return head
```
