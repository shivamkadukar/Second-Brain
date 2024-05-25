- **Dockerfile Overview**:
    
    - A text document with instructions for the Docker engine to build an image.
    - Each instruction adds a new layer to the image.
    - Used to build images from which containers are run.
    - Core component of infrastructure as code.

- **Structure of a Dockerfile**:
    - Organized as a series of instructions, one per line.
    ```bash
    INSTRUCTION arguments
    ```

## Common Dockerfile Instructions

Here’s a list of some common Dockerfile instructions and their purpose:

- `FROM`: Sets the base image to begin with. It is mandatory to have `FROM` as the first instruction in the Dockerfile.
- `WORKDIR`: Sets the working directory for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY` or `ADD` instructions. If the directory does not exist, it will be created automatically.
- `COPY`: Copies files or directories from the host into the container’s file system.
- `ADD`: Similar to `COPY`, but can also handle remote URLs and automatically unpack archives.
- `RUN`: Executes a command within the image as a new layer.
- `CMD`: Defines the default command to execute when running a container from the image.
- `ENTRYPOINT`: Similar to `CMD`, but it’s designed to allow a container as an executable with its own parameters.
- `EXPOSE`: Informs Docker that the container will listen on the specified network ports at runtime.
- `ENV`: Sets environment variables for the container.

## Building an Image from a Dockerfile

To build an image from the Dockerfile, use the `docker build` command, specifying the build context (usually the current directory), and an optional tag for the image.

```
docker build -t my-image:tag .
```

After running this command, Docker will execute each instruction in the Dockerfile, in order, creating a new layer for each.

[[Docker Layer Caching]]
