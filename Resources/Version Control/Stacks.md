> Last in first out

Basic operations we can do on a stack are:
- **Push:** Adds a new element on the stack.
- **Pop:** Removes and returns the top element from the stack.
- **Peek:** Returns the top element on the stack.
- **isEmpty:** Checks if the stack is empty.
- **Size:** Finds the number of elements in the stack.

__Stack Implementation using arrays__

```python
class Stack:
    def __init__(self):
        self.stack = []

    def push(self, element_to_push):
        self.stack.append(element_to_push)

    def peek(self):
        if self.is_empty():
            return "stack is empty"
        return self.stack[-1]

    def pop(self):
        if self.is_empty():
            return "stack is empty"
        return self.stack.pop()

    def is_empty(self):
        return len(self.stack) == 0

    def size(self):
        return len(self.stack)
```

- **Memory Efficient:** Array elements do not hold the next elements address like linked list nodes do.
- **Easier to implement and understand:** Using arrays to implement stacks require less code than using linked lists, and for this reason it is typically easier to understand as well.

- **Fixed size:** An array occupies a fixed part of the memory. This means that it could take up more memory than needed, or if the array fills up, it cannot hold more elements.