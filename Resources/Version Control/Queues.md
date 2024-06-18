> First in first out

Basic operations we can do on a queue are:
- **Enqueue:** Adds a new element to the queue.
- **Dequeue:** Removes and returns the first (front) element from the queue.
- **Peek:** Returns the first element in the queue.
- **isEmpty:** Checks if the queue is empty.
- **Size:** Finds the number of elements in the queue.

__Queue Implementation using Arrays__

```python
class Queue:
    def __init__(self):
        self.queue = []
  
    def enqueue(self, queue_element):
        self.queue.append(queue_element)
  
    def dequeue(self):
        if self.isEmpty():
            return "queue is empty"
        return self.queue.pop(0)
  
    def peek(self):
        if self.isEmpty():
            return "queue is empty"
        return self.queue[0]

    def isEmpty(self):

       return len(self.queue) == 0
  
    def size(self):
        return len(self.queue)
```

- **Memory Efficient:** Array elements do not hold the next elements address like linked list nodes do.
- **Easier to implement and understand:** Using arrays to implement queues require less code than using linked lists, and for this reason it is typically easier to understand as well.

- **Fixed size:** An array occupies a fixed part of the memory. This means that it could take up more memory than needed, or if the array fills up, it cannot hold more elements. And resizing an array can be costly.
- **Shifting cost:** Dequeue causes the first element in a queue to be removed, and the other elements must be shifted to take the removed elements' place. This is inefficient and can cause problems, especially if the queue is long.