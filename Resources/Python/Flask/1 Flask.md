- **Importing Flask**:
    
    - Import the Flask class from the `flask` module.
    ```python
    from flask import Flask
```
    
- **Creating a Flask Instance**:
    
    - Create an instance of the Flask class.
    - The `__name__` argument is used to identify the module or package.
    - This instance will act as the WSGI application.
    
```python
	app = Flask(__name__)
```
    
- **Defining Routes**:
    
    - Use the `route()` decorator to bind a URL to a function.
    - The function associated with the URL is called when that URL is accessed.
    
    ```python
    @app.route("/") 
    def hello_world():
         return "<p>Hello, World!</p>"`
```
    
- **Function Output**:
    
    - The function returns a string that will be displayed in the user’s browser.
    - The default content type is HTML, so HTML in the string will be rendered.
- **Naming and Saving the Application**:
    
    - Save the file as `hello.py` or similar.
    - Avoid naming the file `flask.py` to prevent conflicts with Flask.
- **Running the Application**:
    
    - Use the `flask` command or `python -m flask` to run the application.
    - Specify the application with the `--app` option if needed.
    ```bash
    flask --app hello run
    ```

    - This command starts a local server on `http://127.0.0.1:5000`.
    - Press `CTRL+C` to stop the server.
- **Application Discovery Behavior**:
    
    - If the file is named `app.py` or `wsgi.py`, the `--app` option is not required.
    - Refer to the Flask Command Line Interface documentation for more details.
- **Development Server**:
    
    - The built-in server is suitable for testing but not recommended for production use.
    - For production deployment options, refer to the Flask deployment documentation.
- **Accessing the Application**:
    
    - Open a web browser and navigate to `http://127.0.0.1:5000/` to see the "Hello, World!" greeting.
- **Handling Port Conflicts**:
    
    - If another program is using port 5000, you may encounter an `OSError`.
## Externally Visible Server

- **Local Access by Default**:
  - When you run the server, it is only accessible from your own computer.
  - This default setting prevents security risks, especially in debugging mode.

- **Making the Server Publicly Available**:
  - If the debugger is disabled or if you trust the users on your network, you can make the server accessible from other devices.
  - Add the `--host=0.0.0.0` option to the command line:
    ```bash
    $ flask run --host=0.0.0.0
    ```
  - This command tells the operating system to listen on all public IPs.

## Debug Mode

- **Features of Debug Mode**:
  - Automatically reloads the server if code changes are detected.
  - Shows an interactive debugger in the browser if an error occurs during a request.

- **Security Warning**:
  - The interactive debugger allows executing arbitrary Python code from the browser.
  - It is protected by a PIN, but still represents a significant security risk.
  - **Important**: Do not run the development server or debugger in a production environment.

- **Enabling Debug Mode**:
  - Use the `--debug` option to start the server in debug mode.
    ```bash
    $ flask --app hello run --debug
    ```
  - Output when debug mode is enabled:
    ```
    * Serving Flask app 'hello'
    * Debug mode: on
    * Running on http://127.0.0.1:5000 (Press CTRL+C to quit)
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: nnn-nnn-nnn
    ```
