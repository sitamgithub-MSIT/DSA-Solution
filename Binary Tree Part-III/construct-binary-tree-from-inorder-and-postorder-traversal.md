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
    def buildTree(self, inorder: List[int], postorder: List[int]) -> Optional[TreeNode]:
        """
        Constructs a binary tree from the given inorder and postorder traversal lists.

        Args:
            inorder (List[int]): The inorder traversal list of the binary tree.
            postorder (List[int]): The postorder traversal list of the binary tree.

        Returns:
            Optional[TreeNode]: The root node of the constructed binary tree.
        """

        # If either of the lists is empty then return None
        if not postorder or not inorder:
            return None

        # Create a dictionary to store the index of each value in the inorder list
        dic = {v:i for i, v in enumerate(inorder)}

        def helper(l, r):
            """
            Recursive helper function to construct the binary tree.

            Args:
                l (int): The left index of the current subtree.
                r (int): The right index of the current subtree.

            Returns:
                TreeNode: The root node of the current subtree.
            """

            # If the left index is greater than the right index then return None
            if l > r:
                return None

            # Pop the last element from the postorder list and find its index in the inorder list
            root = TreeNode(postorder.pop())
            idx = dic[root.val]

            # Construct the right and left subtrees
            root.right = helper(idx + 1, r)
            root.left = helper(l, idx - 1)

            # Return the root node
            return root

        # Call the helper function
        return helper(0, len(inorder)-1)
```
