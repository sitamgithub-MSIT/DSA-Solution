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
    def countNodes(self, root: Optional[TreeNode]) -> int:
        """
        Counts the number of nodes in a complete binary tree.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            int: The number of nodes in the binary tree.
        """

        def getHeightLeft(node):
            """
            Helper function to calculate the height of the left subtree.

            Args:
                node: The current node.

            Returns:
                int: The height of the left subtree.
            """
            height = 0
            while(node):
                height += 1
                node = node.left
            return(height)

        def getHeightRight(node):
            """
            Helper function to calculate the height of the right subtree.

            Args:
                node: The current node.

            Returns:
                int: The height of the right subtree.
            """
            height = 0
            while(node):
                height += 1
                node = node.right
            return(height)

        # If the root is empty then return 0
        if root is None:
            return 0

        elif(getHeightLeft(root) == getHeightRight(root)):
            return(2**getHeightLeft(root) - 1)
        else:
            return(1 + self.countNodes(root.left) + self.countNodes(root.right))
```
