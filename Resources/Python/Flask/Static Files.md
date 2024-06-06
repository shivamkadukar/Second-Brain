## Static Files

- **Purpose**:
  - Dynamic web applications often need static files, such as CSS and JavaScript.
  - Ideally, your web server is configured to serve static files, but Flask can serve them during development.

- **Setting Up Static Files**:
  - Create a folder named `static` in your package or next to your module.
  - These files will be available at the `/static` URL on the application.

- **Generating URLs for Static Files**:
  - Use the special `'static'` endpoint name to generate URLs for static files:
    ```python
    url_for('static', filename='style.css')
    ```
  - The file should be stored in the filesystem as `static/style.css`.
