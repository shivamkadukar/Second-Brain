
Understanding Namespaces  
• Namespaces are a Linux kernel feature that isolates system resources.  
• They create an abstraction layer to keep containerized processes separate from each other and the host system.  
  
Types of Namespaces  
• PID (Process IDs): Isolates the process ID number space, allowing processes within a container to see their own processes.  
• Network (NET): Provides each container with a separate view of the network stack.  
• Mount (MNT): Isolates the file system mount points, allowing each container to have its own root file system.  
• UTS (UNIX Time Sharing System): Allows each container to have its own hostname and domain name.  
• User (USER): Maps user and group identifiers between the container and the host.  
• IPC (Inter-Process Communication): Allows or restricts communication between processes in different containers.  
  
Docker's Use of Namespaces  
• Docker creates new namespaces for each container when it is started.  
• Namespaces ensure containers are portable and can run on any system without conflicts or interference.