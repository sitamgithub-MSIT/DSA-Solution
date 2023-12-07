# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->

# Approach
<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(logN)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(1)$$
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
    def findCeil(self,root, inp):
        
        floor = -1
        
        # Traverse the tree
        while root:
            
            # If the root value is equal to the input, return the root value
            if root.data == x:
                return root.data
            
            # If the root value is greater than the input, traverse the left subtree 
            elif root.data > x:
                root = root.left
                
            # If the root value is less than the input, traverse the right subtree
            else:
                floor = root.data
                root = root.right

        # Return the floor  
        return floor

```
