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
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def kthSmallest(self, root: Optional[TreeNode], k: int) -> int:
        """
        Returns the kth smallest element in a binary search tree.

        Args:
            root (Optional[TreeNode]): The root of the binary search tree.
            k (int): The kth smallest element to find.

        Returns:
            int: The kth smallest element in the binary search tree.

        """

        # If the root is None then return
        if root is None:
            return

        # Initialize the count and the stack
        count = 0
        stack = []
        node = root # Start at the root

        # Traverse the tree in inorder
        while node or stack:

            # Traverse the left subtree
            while node:

                # Append the node to the stack and traverse the left subtree
                stack.append(node)
                node = node.left

            # Pop the node from the stack and increment the count
            node = stack.pop()
            count += 1

            # If the count is equal to k then return the value of the node
            if (count == k):
                return node.val

            # Traverse the right subtree
            node = node.right
```
