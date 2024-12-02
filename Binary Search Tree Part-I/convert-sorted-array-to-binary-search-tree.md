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
    def sortedArrayToBST(self, nums: List[int]) -> Optional[TreeNode]:
        """
        Converts a sorted array to a binary search tree.

        Args:
            nums (List[int]): A sorted array of integers.

        Returns:
            Optional[TreeNode]: The root node of the binary search tree.
        """
        def helper(left, right):
            # Base case
            if left > right:
                return

            # Find the middle element
            mid = (left + right)//2
            root = TreeNode(nums[mid])

            # Recursively build the left and right subtrees
            root.left = helper(left, mid-1)
            root.right = helper(mid+1, right)

            # Return the root
            return root

        # Call the helper function
        return(helper(0, len(nums)-1))
```
