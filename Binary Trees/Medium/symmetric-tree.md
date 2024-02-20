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
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        """
        Determines whether a binary tree is symmetric.

        Args:
            root (Optional[TreeNode]): The root node of the binary tree.

        Returns:
            bool: True if the binary tree is symmetric, False otherwise.
        """

        def symmetric(l,r):
            """
            Helper function to check if two nodes are symmetric.

            Args:
                l (TreeNode): The left node.
                r (TreeNode): The right node.

            Returns:
                bool: True if the nodes are symmetric, False otherwise.
            """

            # If both nodes are empty then they are symmetric
            if l is None and r is None:
                return True

            # If one of the nodes is empty then they are not symmetric
            elif l is None or r is None:
                return False

            else:
                # If the values of the nodes are equal then check the left and right subtrees
                if l.val == r.val:
                    return symmetric(l.left,r.right) and symmetric(l.right,r.left)

                # Else return False
                else:
                    return False

        # Call the symmetric function
        return symmetric(root.left,root.right)
```
