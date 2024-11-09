

Containerization is like a VM but ligther

Containerization involves packaging and running applications in isolated environments such as containers, virtual machines, or serverless environments. Technologies like Docker, Docker Compose, and Linux Containers facilitate this on Linux systems, enabling quick, secure, and efficient application deployment and management. Containers are lightweight, allowing for scalability, portability, and the simultaneous running of multiple applications.

Container security is crucial, as containers provide isolation from the host system and other containers, enhancing protection against malicious activities. This isolation and their lightweight nature make containers more secure than traditional virtual machines. Containers are also easy to configure, which supports secure application deployment.

In summary, containerization simplifies application deployment and management, improves efficiency, and enhances security, despite the existence of methods to potentially escalate privileges or escape containers.

#### Docker Run - Syntax

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ docker run -p <host port>:<docker port> -d <docker container name>
```

#### Docker Run

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ docker run -p 8022:22 -p 8080:80 -d FS_docker
```

In this case, we start a new container from the image `FS_docker` and map the host ports 8022 and 8080 to container ports 22 and 80, respectively. The container runs in the background, allowing us to access the SSH and HTTP services inside the container using the specified host ports.

#### Docker Management

When managing Docker containers, Docker provides a comprehensive suite of tools that enable us to easily create, deploy, and manage containers. With these powerful tools, we can list, start and stop containers and effectively manage them, ensuring seamless execution of applications. Some of the most commonly used Docker management commands are:

|**Command**|**Description**|
|---|---|
|`docker ps`|List all running containers|
|`docker stop`|Stop a running container.|
|`docker start`|Start a stopped container.|
|`docker restart`|Restart a running container.|
|`docker rm`|Remove a container.|
|`docker rmi`|Remove a Docker image.|
|`docker logs`|View the logs of a container.|

It is worth noting that these commands, used in Docker, can be combined with various options to provide additional functionality. For example, we can specify which ports to expose, mount volumes, or set environment variables. This allows us to customize our Docker containers to suit our needs and requirements. When working with Docker images, it's important to note that any changes made to an existing image are not permanent. Instead, we need to create a new image that inherits from the original and includes the desired changes.

This is done by creating a new Dockerfile that starts with the `FROM` statement, which specifies the base image, and then adds the necessary commands to make the desired changes. Once the Dockerfile is created, we can use the `docker build` command to build the new image, tagging it with a unique name to help identify it. This process ensures that the original image remains intact while allowing us to create a new image with the desired changes.

It is important to note that Docker containers are designed to be immutable, meaning that any changes made to a container during runtime are lost when the container is stopped. Therefore, it is recommended to use container orchestration tools such as Docker Compose or Kubernetes to manage and scale containers in a production environment.

---

## Linux Containers

Linux Containers (`LXC`) is a virtualization technology that allows multiple isolated Linux systems to run on a single host. It uses resource isolation features, such as `cgroups` and `namespaces`, to provide a lightweight virtualization solution. LXC also provides a rich set of tools and APIs for managing and configuring containers, contributing to its popularity as a containerization technology. By combining the advantages of LXC with the power of Docker, users can achieve a fully-fledged containerization experience in Linux systems.

Both LXC and Docker are containerization technologies that allow for applications to be packaged and run in isolated environments. However, there are some differences between the two that can be distinguished based on the following categories:

- Approach
- Image building
- Portability
- Easy of use
- Security

LXC is a lightweight virtualization technology that uses resource isolation features of the Linux kernel to provide an isolated environment for applications. In LXC, images are manually built by creating a root filesystem and installing the necessary packages and configurations. Those containers are tied to the host system, may not be easily portable, and may require more technical expertise to configure and manage. LXC also provides some security features but may not be as robust as Docker.

On the other hand, Docker is an application-centric platform that builds on top of LXC and provides a more user-friendly interface for containerization. Its images are built using a Dockerfile, which specifies the base image and the steps required to build the image. Those images are designed to be portable so they can be easily moved from one environment to another. Docker provides a more user-friendly interface for containerization, with a rich set of tools and APIs for managing and configuring containers with a more secure environment for running applications.

To install LXC on a Linux distribution, we can use the distribution's package manager. For example, on Ubuntu, we can use the `apt` package manager to install LXC with the following command:

#### Install LXC

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ sudo apt-get install lxc lxc-utils -y
```

Once LXC is installed, we can start creating and managing containers on the Linux host. It is worth noting that LXC requires the Linux kernel to support the necessary features for containerization. Most modern Linux kernels have built-in support for containerization, but some older kernels may require additional configuration or patching to enable support for LXC.

#### Creating an LXC Container

To create a new LXC container, we can use the `lxc-create` command followed by the container's name and the template to use. For example, to create a new Ubuntu container named `linuxcontainer`, we can use the following command:

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ sudo lxc-create -n linuxcontainer -t ubuntu
```

#### Managing LXC Containers

When working with LXC containers, several tasks are involved in managing them. These tasks include creating new containers, configuring their settings, starting and stopping them as necessary, and monitoring their performance. Fortunately, there are many command-line tools and configuration files available that can assist with these tasks. These tools enable us to quickly and easily manage our containers, ensuring they are optimized for our specific needs and requirements. By leveraging these tools effectively, we can ensure that our LXC containers run efficiently and effectively, allowing us to maximize our system's performance and capabilities.

|Command|Description|
|---|---|
|`lxc-ls`|List all existing containers|
|`lxc-stop -n <container>`|Stop a running container.|
|`lxc-start -n <container>`|Start a stopped container.|
|`lxc-restart -n <container>`|Restart a running container.|
|`lxc-config -n <container name> -s storage`|Manage container storage|
|`lxc-config -n <container name> -s network`|Manage container network settings|
|`lxc-config -n <container name> -s security`|Manage container security settings|
|`lxc-attach -n <container>`|Connect to a container.|
|`lxc-attach -n <container> -f /path/to/share`|Connect to a container and share a specific directory or file.|

As penetration testers, we may encounter situations where we must test software or systems with dependencies or configurations that are difficult to reproduce on our machines. This is where Linux containers come in handy. Since a Linux container is a lightweight, standalone executable package containing all the necessary dependencies and configuration files to run a specific software or system, it provides an isolated environment that can be run on any Linux machine, regardless of the host's configuration.

Containers are useful, especially because they allow us to quickly spin up an isolated environment specific to our testing needs. For example, we might need to test a web application requiring a specific database or web server version. Rather than setting up these components on our machine, which can be time-consuming and error-prone, we can create a container that contains the exact configuration we need.

We can also use them to test exploits or malware in a controlled environment where we create a container that simulates a vulnerable system or network and then use that container to safely test exploits without risking damaging our machines or networks. However, it is important to configure LXC container security to prevent unauthorized access or malicious activities inside the container. This can be achieved by implementing several security measures, such as:

- Restricting access to the container
- Limiting resources
- Isolating the container from the host
- Enforcing mandatory access control
- Keeping the container up to date

LXC containers can be accessed using various methods, such as SSH or console. It is recommended to restrict access to the container by disabling unnecessary services, using secure protocols, and enforcing strong authentication mechanisms. For example, we can disable SSH access to the container by removing the `openssh-server` package or by configuring SSH only to allow access from trusted IP addresses. Those containers also share the same kernel as the host system, meaning they can access all the resources available on the system. We can use resource limits or quotas to prevent containers from consuming excessive resources. For example, we can use `cgroups` to limit the amount of CPU, memory, or disk space that a container can use.

#### Securing LXC

Let us limit the resources to the container. In order to configure `cgroups` for LXC and limit the CPU and memory, a container can create a new configuration file in the `/usr/share/lxc/config/<container name>.conf` directory with the name of our container. For example, to create a configuration file for a container named `linuxcontainer`, we can use the following command:

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ sudo vim /usr/share/lxc/config/linuxcontainer.conf
```

In this configuration file, we can add the following lines to limit the CPU and memory the container can use.

Code: txt

```txt
lxc.cgroup.cpu.shares = 512
lxc.cgroup.memory.limit_in_bytes = 512M
```

When working with containers, it is important to understand the `lxc.cgroup.cpu.shares` parameter. This parameter determines the CPU time a container can use in relation to the other containers on the system. By default, this value is set to 1024, meaning the container can use up to its fair share of CPU time. However, if we set this value to 512, for example, the container can only use half of the CPU time available on the system. This can be a useful way to manage resources and ensure all containers have the necessary access to CPU time.

One of the key parameters in controlling the resource allocation of a container is the `lxc.cgroup.memory.limit_in_bytes` parameter. This parameter allows you to set the maximum amount of memory a container can use. It's important to note that this value can be specified in a variety of units, including bytes, kilobytes (K), megabytes (M), gigabytes (G), or terabytes (T), allowing for a high degree of granularity in defining container resource limits. After adding these two lines, we can save and close the file by typing:

- `[Esc]`
- `:`
- `wq`

To apply these changes, we must restart the LXC service.

Containerization

```shell-session
SekhmetCyka@htb[/htb]$ sudo systemctl restart lxc.service
```

LXC use `namespaces` to provide an isolated environment for processes, networks, and file systems from the host system. Namespaces are a feature of the Linux kernel that allows for creating isolated environments by providing an abstraction of system resources.

Namespaces are a crucial aspect of containerization as they provide a high degree of isolation for the container's processes, network interfaces, routing tables, and firewall rules. Each container is allocated a unique process ID (`pid`) number space, isolated from the host system's process IDs. This ensures that the container's processes cannot interfere with the host system's processes, enhancing system stability and reliability. Additionally, each container has its own network interfaces (`net`), routing tables, and firewall rules, which are completely separate from the host system's network interfaces. Any network-related activity within the container is cordoned off from the host system's network, providing an extra layer of network security.

Moreover, containers come with their own root file system (`mnt`), which is entirely different from the host system's root file system. This separation between the two ensures that any changes or modifications made within the container's file system do not affect the host system's file system. However, it is important to remember that while namespaces provide a high level of isolation, they do not provide complete security. Therefore, it is always advisable to implement additional security measures to further protect the container and the host system from potential security breaches.

Here are 9 optional exercises to practice LXC:

|||
|---|---|
|1|Install LXC on your machine and create your first container.|
|2|Configure the network settings for your LXC container.|
|3|Create a custom LXC image and use it to launch a new container.|
|4|Configure resource limits for your LXC containers (CPU, memory, disk space).|
|5|Explore the `lxc-*` commands for managing containers.|
|6|Use LXC to create a container running a specific version of a web server (e.g., Apache, Nginx).|
|7|Configure SSH access to your LXC containers and connect to them remotely.|
|8|Create a container with persistence, so changes made to the container are saved and can be reused.|
|9|Use LXC to test software in a controlled environment, such as a vulnerable web application or malware.|