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
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def bstFromPreorder(self, preorder: List[int]) -> Optional[TreeNode]:
        """
        Constructs a binary search tree from a preorder traversal.

        Args:
            - preorder (List[int]): The preorder traversal of the binary search tree.

        Returns:
            Optional[TreeNode]: The root node of the binary search tree.
        """
        i = 0

        def build(preorder, bound):
            nonlocal i
            if i == len(preorder) or preorder[i] > bound:
                return None

            root = TreeNode(preorder[i])
            i += 1

            # Recursively build the left and right subtrees
            root.left = build(preorder, root.val)
            root.right = build(preorder, bound)

            # Return the root
            return root

        # Call the build function
        return build(preorder, float('inf'))
```
