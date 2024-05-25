Reference - [Deprecated python package](https://pypi.org/project/Deprecated/)

Give function deprecation warning before ahead of time before removing the function from code-base.

```python
from deprecated import deprecated

# reason = reason for deprecation, new method to replace the deprecated method

# version = version from which the method has been deprecated

@deprecated(reason='This method is deprecated, use add and sub method for respective operation', version='1.5.4')

def calculation(a, b, operaation):
	return eval(f'{a} {operaation} {b}')

def add(a, b):
	return a+b

def sub(a, b):
	return a-b
```

![[Screenshot from 2024-05-11 09-56-06.png|1000]]