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
    def deleteNode(self, root: Optional[TreeNode], key: int) -> Optional[TreeNode]:
        """
        Deletes a node with the given key from the binary search tree.

        Args:
            root (Optional[TreeNode]): The root of the binary search tree.
            key (int): The key of the node to be deleted.

        Returns:
            Optional[TreeNode]: The root of the modified binary search tree.

        """

        # If the root is None then return None
        if root is None:
            return

        # If the value is less than the root value, traverse the left subtree
        if root.val > key:
            root.left = self.deleteNode(root.left, key)

        # If the value is greater than the root value, traverse the right subtree
        elif root.val < key:
            root.right = self.deleteNode(root.right, key)

        # If the root value is equal to the key
        else:

            # If the root has no left child
            if not root.left:
                return root.right

            # If the root has no right child
            elif not root.right:
                return root.left

            # If the root has both left and right children
            curr = root.right

            # Find the minimum value in the right subtree
            while curr.left:
                curr = curr.left

            # Replace the root value with the minimum value in the right subtree
            root.val = curr.val
            root.right = self.deleteNode(root.right, curr.val)

        # Return the root
        return root
```
