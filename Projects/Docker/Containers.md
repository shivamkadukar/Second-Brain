Reference - https://www.docker.com/resources/what-container/

### Containers: Lightweight, Portable Software Environments  
• Allow developers to run and package applications consistently across different platforms.  
• Streamlines application development, deployment, and management processes.  
  
Working Principles of Containers  
• Share the host’s OS kernel and leverage lightweight virtualization techniques.  
• Provide efficiency by sharing common libraries and executable files.  
• Encapsulate applications and their dependencies for easy movement and consistent running across different environments.  
• Offer fast startup and shutdown due to no need to boot a full OS.  
• Provide a consistent environment for application development, testing, and production.  
  
Docker and Containers  
• Docker simplifies the creation, deployment, and management of containers.  
• Provides tools and APIs for managing containerized applications.

### Need for Containers in Software Development  
  
• Challenges in deploying applications across different environments: Inconsistent environments, inefficient resource utilization, and slow processes.  
• Solution: Containers solve these by bundling an application and its dependencies into a single container, ensuring smooth operation across different environments.  
• Advantages: Containers share underlying system resources and OS kernel, making them lightweight and efficient.  
• Benefits: Faster development and deployment cycles due to easy creation, destruction, and replacement.  
• Impact: Containers revolutionize modern software development practices, ensuring reliable and consistent software delivery.


### Bare Metal vs VM vs Containers Overview  
  ![[Pasted image 20240509144121.png]]
Bare Metal:  
• A computer running directly on hardware without virtualization.  
• Most performant but least flexible.  
• Can only run one application per server.  
• Cannot easily move applications to another server.  
  
Virtual Machines:  
• Run multiple applications on a single server.  
• Run on top of a hypervisor.  
• Allows running multiple operating systems on a single server.  
• Provides isolation between applications running on different VMs.  
  
Containers:  
• Run multiple applications on a single server without a hypervisor.  
• Run on top of a container engine.  
• Provides isolation between applications running on different containers.

### Docker and OCI: A Collaboration  
  
• [The Open Container Initiative (OCI)](https://opencontainers.org/) is a Linux Foundation project aiming to create industry standards for container formats and runtimes.  
• Docker, a founding member of OCI, has significantly shaped standards for container formats and runtimes.  
• Docker's container runtime and image format, Dock Engine and Image, form the basis for OCI specifications.  
• OCI has two main specifications: Runtime Specification (runtime-spec) and Image Specification (image-spec).  
• Docker's commitment to supporting OCI standards has led to continuous updates to be compliant with OCI standards.  
• Docker's containerd runtime and image format are fully compatible with OCI specifications, enabling compatibility between Docker containers and other OCI-compliant runtimes.