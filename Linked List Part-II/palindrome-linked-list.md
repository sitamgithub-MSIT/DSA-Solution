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
    def isPalindrome(self, head: Optional[ListNode]) -> bool:
        """
        Determines if a singly linked list is a palindrome.

        Args:
            head (Optional[ListNode]): The head of the linked list.

        Returns:
            bool: True if the linked list is a palindrome, False otherwise.
        """
        nums = []

        # Traverse the linked list and store the values in a list
        while head:
            nums.append(head.val)
            head = head.next

        # Check if the list is palindrome
        l, r = 0, len(nums)-1
        while(l <= r):
            # If the values at the left and right pointers are not equal, return False
            if nums[l] != nums[r]:
                return False

            # Move the pointers
            l, r = l+1, r-1

        # Return True if the list is palindrome
        return True
```
