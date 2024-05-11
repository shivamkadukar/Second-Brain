- **A client application:**
    - _**Command Line Interface (CLI):**_ Interact with Docker using commands like`docker run` or `docker pull`.
    - _**Graphical User Interface (GUI):**_ Browse images, configure CPU, memory, and disk space allocation.
    - _**Credential Helper:**_ Store credentials for private registries.
    - _**Extensions:**_ Third-party software that provides additional functionality.
- **A Linux virtual machine containing:**
    - **Docker daemon (dockerd):** Manages container objects, networking, and volumes within the server host application. It exposes the Docker API for communication with the client application.
    - **(Optional) Kubernetes cluster**

![[Pasted image 20240509165303.png]]