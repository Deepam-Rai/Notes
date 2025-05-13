https://docs.docker.com/get-started/docker-overview/

> **Docker daemon `dockerd`**: listens for Docker API requests and manages docker objects such as images, containers, networks and volumes.

> **Docker client `docker`**: primary way that users interact with Docker.

- Docker client communicates with Docker daemon using REST API

> **Docker registry**: Centralized location that stores and manages images.

- **Repository**: Collection of a related container images within a registry.
- Docker Hub is a public Docker registry and by default used registry.

**Docker objects:**
- **Image**: Read-only template with instructions for creating a Docker container.
	- **Dockerfile**: Script containing series of instructions used to build a Docker Image.
	- **Tags**: Allows to label and version images.
- **Container**: Runnable instance of an Image.

Commands:
```shell
# image search
docker search <namespace>/<repository>

# image pull
docker pull <namespace>/<repository>

# list local images
docker image ls

# list image layers
docker image history <image-name>
docker image history --no-trunc ...  # viewing full commands

# check container low-level information
docker inspect <container>

# Tagging image during build
docker build -t <namespace>/<respository> .

# Tagging already built image
docker image tag <built-image> <namespace>/<repository>:tag

# Tagging for private registry
docker image tag <image> <registry>:<port>/<namespace>/<respository>:<tag>

# Publishing images
docker push <namespace>/<repository>:tag
```

# Building images

## Raw method
Creating base image:
```shell
# Create a new container from base-image
# open shell in the container
docker run --name=base-container -ti <base-image>

# Install/make changes inside the container
# Example: Install Node:
apt update && apt install nodejs;
# verify node is installed
node -e "console.log('Node installed!')"

# In another terminal
# save the changes as new Image layer
docker container commit -m "Added nodejs" base-container node-base

# view the layers of new image
docker image history node-base

# start new container using new image
docker run node-base node -e "console.log('From node-base image')"

# remove the base-container
docker rm -f base-container
```

Creating app image:
```shell
# Using the node-base base image from previous section
docker run --name=app-container -ti node-base

# Add app logic
# Example: Create a simple node program
echo 'console.log("Hello from an app")' > app.js
# verify node app
node app.js

# In another terminal
# save the changes as new-layer
docker container commit -c "CMD node app.js" -m "Added app" app-container sample-app
# Have also set a default command on container start: `node app.js`

# Check new image layers
docker image history sample-app

# Start new container using app-image
docker run sample-app

# remove the app-container used while creating app-image
docker rm -f app-container
```

## Writing Dockerfile
`Dockerfile` equivalent to previous section:
```shell
FROM ubuntu

WORKDIR /usr/local/app

RUN apt update && apt install -y nodejs

COPY app.js ./app.js

RUN useradd app

USER app

CMD ["node", "app.js"]
```
where `app.js` contains:
```js
console.log("Built from Dockerfile")
```

Building image:
```shell
docker build -t sample2-app .
```

Running container with the image:
```shell
docker run sample2-app
```

# Running Containers

## Publishing and exposing ports

During container creation:
```shell
docker run -d -p <host-port>:<container-port> <image>
```
 
 Publishing to ephemeral ports:
```shell
docker run -d -P <container-port> <image>
```

Exposing port in Dockerfile:
```
EXPOSE <port-number>
```
- this indicates that packaged application will use that port, but **it is not published by default.**
Publishing all exposed ports to ephemeral port:
```shell
docker run -d -P <image>
```

## Overriding container defaults

```shell
# Exposing and publishing port
docker run -d -p <host-port>:<container-port> <image>

# Setting env var. Example: `env`=`dev`
docker run -e env=dev <image> env
# the `env` at last commands container to show its environment vars.

# Setting env vars using env var. File: `.env`
docker run --env-file .env <image> env

# Restricting memory and cpu
docker run -ti --memory="512m" --cpus="0.5" <image>
```


### Controlled network
By default container connect to special network called `bridge`
- each container is assigned unique IP
- containers in same host can connect with each other via this IP
- but isolates them from other hosts.

Custom networks
```shell
# list networks
docker network ls

# create network
docker network create <name>

# Connecting container to a network
docker network connect <network> <container>
# restart and exec into it
docker restart <container>
docker exec -ti <container> /bin/bash

# Connecting network while creating container
docker run -ti --name=<container> --network <network> <image>

```

## Persisting container data
> **Volumes**: are separate directories managed by docker independent of host filesystem.

```shell
# list all volumes
docker volume ls

# Creating volume
docker volume create <name>

# Starting a container with volume attached
docker run -ti -v <volume-name>:<path-in-container> <image>

# deleting volume
docker volume rm <volume>
# only works if not attached to any container

# deleting un-attached volumes
docker volume prune
```

# Docker system commands
```shell
docker system --help

# info
docker system info

# disk usage
docker system df
docker system df -v
```