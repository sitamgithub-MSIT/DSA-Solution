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
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Merges two sorted arrays, nums1 and nums2, into nums1 in sorted order.

        Args:
            nums1 (List[int]): The first sorted array.
            m (int): The number of elements in nums1.
            nums2 (List[int]): The second sorted array.
            n (int): The number of elements in nums2.

        Returns:
            None: The function modifies nums1 in-place.
        """

        k = m + n -1

        # Iterate through the arrays
        while m > 0 and n > 0:

            # If the last element of nums1 is greater than the last element of nums2, set the last element of nums1 to the last element of nums1
            if nums1[m-1] > nums2[n-1]:
                nums1[k] = nums1[m-1]
                m -= 1

            # Otherwise, set the last element of nums1 to the last element of nums2
            else:
                nums1[k] = nums2[n-1]
                n -= 1

            # Decrement k
            k -= 1

        # If there are elements left in nums2, set them to nums1
        while(n > 0):

            # Set the last element of nums1 to the last element of nums2
            nums1[k] = nums2[n-1]

            # Decrement n and k
            n -= 1
            k -= 1
```
