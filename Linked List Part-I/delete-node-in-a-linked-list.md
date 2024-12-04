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
    def deleteNode(self, node):
        """
        Deletes a node in a singly linked list.

        Args:
            node: The node to be deleted.

        Returns: None
        """
        # if node is None, return
        if node is None:
            return

        # if node.next is None, delete node
        if(node.next == None):
            del node

        # copy the value of the next node to the current node
        node.val = node.next.val
        node.next = node.next.next
```
