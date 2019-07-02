---
title: Install Docker Toolbox
layout: tutorial
---

How to INSTALL DOCKER TOOLBOX FOR WINDOW
This is the instruction of how to install docker for window 
- Suggested for Window 7 up to Window 10
- Not for Window 10 Pro and Window 10 Education
- !! Before that!! let install some important tool for support docker

**Installation**
- 1.Please install [Git & Python](/installs/Gitpython.html)
- 2.Text Editor installation Ex. [Visual Studio code](https://code.visualstudio.com/) or [Notepad++](https://notepad-plus-plus.org/download/v7.7.1.html) or [Wordpad](https://microsoft_wordpad.en.downloadastro.com/)
- 3.Installation Docker

# Installation Docker

Docker is a set of coupled software-as-a-service and platform-as-a-service products that use operating-system-level virtualization to develop and deliver software in packages called containers. The software that hosts the containers is called Docker Engine. It can build likes docker images or build from another type of file. Example likes you can build jekyll(Simple,blog-aware of static site),docker will find the images and install by using **`docker run`** command. It can be pull database that support in docker likes mariadb too. 

## Docker Toolbox

Docker can be use by **`Docker Toolbox`** an installer that easily make user can set up an environment on your machine or create virtuak machine that contain **`Docker Quickstart`** for type in docker,**`Docker Desktop`** for Window 10 PRO, Window 10 Education or higher. Docker have **`docker hub`** to keep information, project or repository the same as git. This document will only give information about **`Docker Toolbox`** only.

1.Docker Toolbox for window 7 up to window 10(not for PRO or Education)

- Go to website [https://docs.docker.com/toolbox/overview/](https://docs.docker.com/toolbox/overview/)

![Docker](/assets/docker1st.jpg)

- Available for MAC and WINDOWS, Click downloads for MAC or WINDOWs. You can see detail of an instruction below the download file.

![DockerAvaWin](/assets/docker2nd.jpg)

- When you finished download, open file.exe to see Set up Docker toolbox page

![Dockersetup](/assets/docker3rd.jpg)

2.Choose the component that you want to use in this i choose docker client,machine and compose for window
- **`docker client`** for running Docker Engine to create images and containers
- **`docker machine`** for run Docker Engine commands from Windows terminals
- **`docker compose for window`** for running the docker-compose command

Also contain Kinematic,Oracle VM and Shell , you can choose what you have to use.

- **`Kitematic`** the Docker GUI
- **`Shell`** preconfigured for a Docker command-line environment.
- **`Oracle Virtualbox`**
 
Docker Engine daemon uses Linux-specific kernel features, you can’t run Docker Engine natively on Windows. Instead, you must use the Docker Machine command, **`docker-machine`**, to create and attach to a small Linux VM on your machine. This VM hosts Docker Engine for you on your Windows system.

![DockerComponent](/assets/docker4th.jpg)

3.Then Click **`Next>>`** until they already done installation

![DockerDone](/assets/docker5th.jpg)

4.When it already finish, this icon will be shown on your desktop
- the Docker QuickStart shell preconfigured for a Docker command-line environment

![DockerQuickstarticon](/assets/docker6th.jpg)

5.Double click **`Docker Quickstart`** and waiting for complie and execute for a while
- This step will verify the installation of your computer whether everything is already install or not

![DockerQuickstartComplie](/assets/docker7th.jpg)

- The terminal does several things to set up Docker Toolbox for you. When it is done, the terminal displays the $ prompt.

![DockerQuickstart](/assets/docker8th.jpg)

6.When execute done double click again it will shown like this and done

![DockerQuickstartpage](/assets/docker9th.jpg)

7.For checking The Docker installation again, by run
    {% raw %}
    $ docker run hello-world
    {% endraw %}

![DockerHelloworld](/assets/docker10th.jpg)

- if it shown likes this its done

8.Check in Docker quickstart terminal whether you already install all of the material or program that have to use by using
    {% raw %}
    $ docker --version
    $ python --version
    $ pip --version
    $ git --version
    {% endraw %}

![CheckVersion](/assets/docker11th.jpg)

# How to Uninstall Docker Toolbox
[Docker Uninstall instruction](https://docs.docker.com/toolbox/toolbox_install_windows/)


