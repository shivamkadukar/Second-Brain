**How it works:**

1. Create a new array for counting how many there are of the different values.
2. Go through the array that needs to be sorted.
3. For each value, count it by increasing the counting array at the corresponding index.
4. After counting the values, go through the counting array to create the sorted array.
5. For each count in the counting array, create the correct number of elements, with values that correspond to the counting array index.

```python
my_array = {array to be sorted}
count_array = [0] * (max(my_array) + 1)

while len(my_array):
    count_array[my_array[0]] += 1
    my_array.pop(0)


for i in range(len(count_array)):
    while count_array[i] > 0:
        my_array.append(i)
        count_array[i] -= 1

print(my_array)
```

__Time Complexity of Counting Sort__

the Counting Sort algorithm runs fast when the range of possible values k is smaller than the number of values n.

- Finding the maximum value: Every value must be evaluated once to find out if it is the maximum value, so n𝑛 operations are needed.
- Initializing the counting array: With k𝑘 as the maximum value in the array, we need k+1𝑘+1 elements in the counting array to include 0. Every element in the counting array must be initialized, so k+1𝑘+1 operations are needed.
- Every value we want to sort is counted once, then removed, so 2 operations per count, 2⋅n2⋅𝑛 operations in total.
- Building the sorted array: Create n𝑛 elements in the sorted array: n𝑛 operations.

$$
Operations = n + (k + 1) + 2n + n
			= 4.n + k + 1 
			\approx 4n + k 
			\approx O(n + k)
$$