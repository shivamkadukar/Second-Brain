__How to select which algo to use for a given condition__
- Is stability imports?
- Is time the concern?
- Is space the concern?

### Bubble Sort
- Time Complexity - O(n^2)
- Space Complexity - O(1)

```python
def bubble_sort(array):
    # Iterate through the array multiple times, each time moving the largest unsorted element to the end
    for i in range(len(array) - 1): 
        swapped = False  # Flag to track if any swaps were made in this pass
        
        # Iterate through the unsorted part of the array
        for j in range(len(array) - i - 1): 
            # Compare adjacent elements and swap if necessary to move the larger element towards the end
            if array[j] > array[j+1]:
                array[j], array[j+1] = array[j+1], array[j]  # Swap the elements
                swapped = True  # Mark that a swap occurred in this pass
                
        # If no swaps were made in this pass, the array is already sorted
        if not swapped:
            break  # Exit the loop as the sorting is complete
```
