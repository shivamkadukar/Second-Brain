### Linear Search

```python
def linear_search(array, number):
	for index, element in enumerate(array):
		if element == number:
			return index
	return None
```

- Time Complexity - O(n)
- Space Complexity - O(1)

### Binary Search

- Faster than linear search
- We can eliminate half of the remaining element at a time, instead of one by one.
- Only works with __sorted arrays__

```python
def binary_search(array, number):
	start = 0
	end = len(array) - 1
	middle = math.floor((start + end)/2)
	while array[middle] != number and start<=end:
		if array[middle] > number:
			end = middle - 1
		else:
			start = middle + 1
		middle = math.floor((start + end)/2)
	if array[middle] == number:
		return middle
	else
		return -1
	
```

- Time Complexity - Best case - O(1), Worst Case - O(logn)
- Space complexity - O(1)

