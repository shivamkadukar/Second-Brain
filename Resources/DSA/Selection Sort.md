**How it works:**

1. Go through the array to find the lowest value.
2. Move the lowest value to the front of the unsorted part of the array.
3. Go through the array again as many times as there are values in the array.

```python
my_array = [64, 34, 25, 5, 22, 11, 90, 12]

n = len(my_array)
for i in range(n-1):
    min_index = i
    for j in range(i+1, n):
        if my_array[j] < my_array[min_index]:
            min_index = j
    min_value = my_array.pop(min_index)
    my_array.insert(i, min_value)

print("Sorted array:", my_array)
```

__Selection sort shifting problem__

Each time the lowest value array element is removed, all following elemnets must be shifted one place down to make up for removal.
![[Pasted image 20240612222226.png]]
 After the lowest value (5) is found and removed, it is inserted at the start of the array, causing all following values to shift one position up to make space for the new value,
![[Pasted image 20240612222256.png]]

> Solution: swap values, instead of shifting


```python
my_array = [64, 34, 25, 5, 22, 11, 90, 12]

n = len(my_array)
for i in range(n-1):
    min_index = i
    for j in range(i+1, n):
        if my_array[j] < my_array[min_index]:
            min_index = j
    my_array[i], my_array[min_index] = my_array[min_index], my_array[i]

print("Sorted array:", my_array)
```

__Time complexity of selection sort__

$$
Operations = (n-1).n/2 + n
			= n^2/2 - n/2 + n
			= n^2/2 + n/2
$$
$$ Operations = n^2/2 + n/2 \approx n^2/2
$$
$$
O(1/2. n^2) = O(n^2)
$$

