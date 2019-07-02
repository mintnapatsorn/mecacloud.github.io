---
title: Docker Toolbox & Docker Overview
layout: tutorial
installs:
# - title: Docker Toolbox Overview
#   url: "/tutorials/Docker.html"
# - title: Ready for Docker
#   url: "/tutorials/Document.html"
---

Docker is a set of coupled software-as-a-service and platform-as-a-service products that use operating-system-level virtualization to develop and deliver software in packages called containers. The software that hosts the containers is called Docker Engine. It can build likes docker images or build from another type of file. Example likes you can build jekyll(Simple,blog-aware of static site),docker will find the images and install by using **`docker run`** command. It can be pull database that support in docker likes mariadb too. Docker can be use by **`Docker Toolbox`** like in this documents that contain **`Docker Quickstart`** for type in docker,**`Docker Desktop`** for Window 10 PRO, Window 10 Education or higher. Docker have **`docker hub`** to keep information, project or repository the same as git. 

**`Docker Images `**  Set of file that keep program inside docker containers. User can be export the images out of VM and then push into other computer. Command to see whether it have image or not using
```
$ Docker Images ls
``` 
or 

```
$ Docker Images
```

**`Docker Container`** A box of VM contain virtual environment and keep images inside. When user run image it will become container that each of container have a container ID to identify each of them. User can also commit this container to keep it and using it likes an images. Command
```
$ Docker Containers
```

This document will only give information about **`Docker Toolbox`** only.

# DOCKER TOOLBOX OVERVIEW


Docker Toolbox is the fastest way to get up and running with docker development that can make you running Virtual machine on your default machine easily. Docker Toolbox is also an installer that easily make user can set up an environment on your machine. Docker Toolbox will available on MAC and Window. Composed of

- **Docker Client** - docker binary, communicate with user, user can be run docker command in this part and create `docker images` and `docker containers` 

- **Docker Machine** - docker-machine binary, run Docker Engine commands from Windows terminals

- **Docker Compose** - docker-compose binary, running the docker-compose command

- **Kitematic** – Desktop GUI for Docker

- **Docker Quickstart** - Terminal app, command-line environment.

- **Oracle Virtualbox** - VM that contain OS X system inside, in this part their using boot2docker.

- **Boot2docker** - Lightweight Linux system, make docker can be run in environment the same with linux environment and then push docker client to user.

- **Docker Daemon** - When you already run the docker command through docker client, docker client will sent the command to docker daemon or can called docker server to generate command and find the result.

<!-- ![Docker daemon](/assets/docker daemon.jpg) -->

# How Docker toolbox communicate to other composed.

![Docker](/assets/Docker.jpeg)

1.When you run the docker command like **`Docker run`**,**`Docker build`**,**`Docker pull`** or others command in Docker quickstart terminal or kinematic, Docker client in docker toolbox will send the command to docker daemon. 

2.Then Docker Daemon will generate **`Docker container`** or **`Docker images`** or it can be pull the images from this container to another container. Docker daemon can also download the images that doesn't have in docker images from their repository of docker hub automatically. Docker daemon ends up running in a virtual machine that uses Linux, and the Docker client is configured to connect to that remote Docker host.

3.A place where to find docker images from registry and download it.

