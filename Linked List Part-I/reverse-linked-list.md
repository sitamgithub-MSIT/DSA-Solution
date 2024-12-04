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
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        """
        Reverses a singly linked list.

        Args:
            head (Optional[ListNode]): The head node of the linked list to be reversed.

        Returns:
            Optional[ListNode]: The new head node of the reversed linked list, or None if the input list is empty.
        """
        # if head is None, return None
        if head is None:
            return

        # if head.next is None, return head
        if head.next is None:
            return head

        # initialize the current and previous node
        curr = head
        pre = None

        while(curr is not None):
            next_head = curr.next
            curr.next = pre
            pre = curr
            curr = next_head

        # return the reversed linked list
        return pre
```
