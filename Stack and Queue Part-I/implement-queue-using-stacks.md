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
class MyQueue:

    def __init__(self):
        # Initialize the stack
        self.stack = []

    def push(self, x: int) -> None:
        # Append the element to the stack
        self.stack.append(x)

    def pop(self) -> int:
        # Pop the first element from the stack
        if self.stack:
            ele = self.stack.pop(0)

            # Return the element
            return ele

    def peek(self) -> int:
        # Return the first element from the stack
        if self.stack:
            return(self.stack[0])

    def empty(self) -> bool:
        # Check if the stack is empty
        if self.stack:
            return False

        # Return True if the stack is empty
        else:
            return True


# Your MyQueue object will be instantiated and called as such:
# obj = MyQueue()
# obj.push(x)
# param_2 = obj.pop()
# param_3 = obj.peek()
# param_4 = obj.empty()
```
