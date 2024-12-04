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
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def middleNode(self, head: Optional[ListNode]) -> Optional[ListNode]:
        """
        Finds the middle node of a singly linked list.

        Args:
            head (Optional[ListNode]): The head node of the linked list.

        Returns:
            Optional[ListNode]: The middle node of the linked list. If the list is empty, returns None.
        """
        # if head is None, return None
        if head is None:
            return

        # if head.next is None, return head
        if head.next is None:
            return head

        # initialize the fast and slow pointer
        fast = head
        slow = head

        # move the fast pointer twice as fast as the slow pointer
        while(fast and fast.next):
            slow = slow.next
            fast = fast.next.next

        # return the middle node
        return slow
```
