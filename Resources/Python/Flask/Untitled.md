# Web Development with Flask

## HTML Escaping

- **Purpose**:
  - Protects from injection attacks when returning HTML.
  - Automatically handled by Jinja templates.

- **Manual Escaping**:
  - Use `escape()` from the `markupsafe` module to escape user-provided values.
  ```python
  from markupsafe import escape

  @app.route("/<name>")
  def hello(name):
      return f"Hello, {escape(name)}!"
```
## Routing

- **Purpose**:
    
    - Uses meaningful URLs to help users remember and access pages directly.
- **Basic Routing**:
    
    - Bind a function to a URL using the `route()` decorator.
    
    python
    
    Copy code
    
    ```python
    @app.route('/')
     def index():
          return 'Index Page'
	@app.route('/hello')
	 def hello():
	      return 'Hello, World'```
    
- **Dynamic URLs**:
    
    - Make parts of the URL dynamic using `<variable_name>`.
    - Use converters to specify the argument type: `<converter:variable_name>`.
    
    python
    
    Copy code
    
    ```python
    from markupsafe import escape
    @app.route('/user/<username>')
     def show_user_profile(username):     
	    return f'User {escape(username)}'
	@app.route('/post/<int:post_id>')
	 def show_post(post_id):
	      return f'Post {post_id}'
	@app.route('/path/<path:subpath>')
	 def show_subpath(subpath):
	      return f'Subpath {escape(subpath)}'```
    
- **Converter Types**:
    
    - `string`: (default) accepts any text without a slash.
    - `int`: accepts positive integers.
    - `float`: accepts positive floating point values.
    - `path`: like string but also accepts slashes.
    - `uuid`: accepts UUID strings.