- **Container Images**:
    - Executable packages that include everything required to run an application.
    - Contain code, runtime, system tools, libraries, and settings.
    - Enable seamless deployment of applications with all dependencies on any Docker-supported platform.
- **[[Dockerfile]]**:
    - Key component for building a container image.
    - Script with instructions on assembling a Docker image.
    - Each instruction creates a new layer in the image, aiding in tracking changes and minimizing image size.

    **Building A Image**:
	- Execute in the terminal from the directory containing the Dockerfile.
	- Builds an image using the Dockerfile in the current directory and assigns it a name.
```bash
	docker build -t your-image-name
```
- **Inspecting Images and Layers**:
```bash
# List images: 
docker image ls
# View individual layers of an image: 
docker history your-image-name
# Inspect an image: 
docker inspect your-image-name
# Remove an image: 
docker image rm your-image-name
```

- **Pushing Images to a Registry**:
```bash
# Log in to the registry: 
docker login
# Tag the image with the registry URL: 
docker tag your-image-name username/repository:tag
# Push the tagged image to the registry: 
docker push username/repository:tag
```
- **Summary**:
    - Building container images is essential for packaging and deploying applications.
    - A Dockerfile with precise instructions facilitates effortless building and distribution of images across various platforms.