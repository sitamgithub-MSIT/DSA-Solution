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
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        """
        Removes the nth node from the end of a singly linked list.

        Args:
            - head (Optional[ListNode]): The head node of the linked list.
            - n (int): The index of the node to be removed.

        Returns:
            Optional[ListNode]: The head node of the linked list after removing the nth node from the end.
        """
        # initialize the slow and fast pointer
        slow = head
        fast = head

        # move the fast pointer n steps ahead
        for _ in range(n):
            fast = fast.next

        if fast is None:
            return head.next

        # move the slow and fast pointer until the fast pointer reaches the end
        while fast.next:
            fast = fast.next
            slow = slow.next

        # remove the nth node from the end
        slow.next = slow.next.next

        # return the head of the linked list
        return head
```
