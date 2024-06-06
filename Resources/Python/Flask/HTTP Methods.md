- By default, route only answers to `GET` requests.
- Method is specified in the route decorater in `method` argument, can specify multiple methods.
> multiple methods can be kept in one function, if they uses common data.

```python
from flask import request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        return do_the_login()
    else:
        return show_the_login_form()
```

- Views for different methods can be separated with different functions.
- shortcut routes - `get() and post()`

```python
@app.get('/login')
def login_get():
    return show_the_login_form()

@app.post('/login')
def login_post():
    return do_the_login()
```

> If `GET` is present, `HEAD` is supported by default, `OPTIONS` is automatically implemented