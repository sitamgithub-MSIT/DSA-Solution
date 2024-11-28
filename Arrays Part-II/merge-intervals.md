# Intuition

<!-- Describe your first thoughts on how to solve this problem. -->

# Approach

<!-- Describe your approach to solving the problem. -->

# Complexity

- Time complexity: $$O(nlogn)$$
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity: $$O(n)$$
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code

```
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        """
        Merge overlapping intervals in a list of intervals.

        Args:
            intervals (List[List[int]]): A list of intervals, where each interval is represented as alist of two integers [start, end].

        Returns:
            List[List[int]]: A list of merged intervals, where each interval is represented as a list oftwo integers [start, end].
        """
        # Sort the intervals based on the start time
        intervals.sort(key = lambda interval:interval[0])
        res = [intervals[0]]

        # Iterate through the intervals
        for start, end in intervals[1:]:

            # If the end time of the last interval is less than the start time of the current interval, append the current interval
            if res[-1][1] < start:
                res.append([start, end])

            # Otherwise, update the end time of the last interval
            else:
                res[-1][1] = max(res[-1][1], end)

        # Return the merged intervals
        return res
```
