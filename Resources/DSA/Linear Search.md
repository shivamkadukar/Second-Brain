**How it works:**

1. Go through the array value by value from the start.
2. Compare each value to check if it is equal to the value we are looking for.
3. If the value is found, return the index of that value.
4. If the end of the array is reached and the value is not found, return -1 to indicate that the value was not found.

```python
target_value = {some_value}
def linear_search(target_value, my_array):
	for i in range(len(my_array)):
		if my_array[i] == target_value:
			return i
	return -1
```

Best Case: O(1)
Worst case: O(n)
