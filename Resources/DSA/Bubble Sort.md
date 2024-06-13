**How it works:**

1. Go through the array, one value at a time.
2. For each value, compare the value with the next value.
3. If the value is higher than the next one, swap the values so that the highest value comes last.
4. Go through the array as many times as there are values in the array.

```python
my_array = [7, 3, 9, 12, 11]

n = len(my_array)
for i in range(n-1):
    swapped = False
    for j in range(n-i-1):
        if my_array[j] > my_array[j+1]:
            my_array[j], my_array[j+1] = my_array[j+1], my_array[j]
            swapped = True
    if not swapped:
        break

print("Sorted array:", my_array)
```


__[[Time complexity]] of Bubble Sort__

$$
Operations=(n−1)⋅n/2=n^2/2−n/2
$$
If n is too big, so will be the n^2 ,
$$
Operations = n^2/2 - n/2 \approx n^2/ = (1/2).n^2
$$
Factors are disregarded in Big O notations,
$$
O(1/2. n^2) = O(n^2)
$$
