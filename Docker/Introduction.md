# Docker stack
![docker stack](Images/Docker/docker_stack.jpg)


> **Docker:** is **a software platform that allows you to build, test, and deploy applications quickly**.

>**Docker container image:** is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

## Docker Engine
> **Docker Engine:** The core component of docker, that manages containerization of applications.

Acts as client server application with:
- A server with long-running daemon process `dockerd`.
- APIs with which programs can talk and instruct docker daemon.
- Command Line Interface(CLI) client `docker`.

![docker engine](Images/Docker/docker_engine.png)

![docker engine architecture](Images/Docker/docker_engine_architecture.avif)

# Docker compose
>**Docker compose:** is a tool for defining and running multi-container applications.

- Simplifies config: Config of whole multi-container setting for images and services is defined in YAML file.
- Simplifies management: Starts and manages the entire app according to config.
We specify the docker compose file during start up of application and the docker engine starts the application according to the config inside the file.

![docker compose](Images/Docker/docker_compose.png)
# Swarm mode
[Docker swarm note](./Docker%20Swarm.md)
> **Swarm mode:** is advanced feature for managing a cluster of docker daemons.

![docker swarm](Images/Docker/docker_swarm.png)

----
# Benefits of Docker
1. Portable, loosely coupled.
2. Scalable.
3. Lightweight, compared to VMs.
4. 

# Container vs VM

![docker vs vm](Images/Docker/container_vs_vm.png)


