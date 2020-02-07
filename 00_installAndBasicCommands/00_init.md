### What is a Container?

> *A container is a standard unit of software that packages up code and all its dependencies*
> *so the application runs quickly and reliably from one computing environment to another.*
> *A Docker container image is a lightweight, standalone, executable package of software* 
> *that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.*

[![N|Solid](https://www.docker.com/sites/default/files/d8/styles/large/public/2018-11/container-what-is-container.png?itok=vle7kjDj)](https://www.docker.com/why-docker)

## Installation

There are many way to install Docker, one of them is Install Using Script. PD: You should review anithing script download from internet for you security.

```
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
```
If you would like to use Docker as a non-root user, you should now consider adding your user to the “docker” group with something like:
```
sudo usermod -aG docker your-user
```

## Activitys

During the discovery of Docker and Dry Tool like tool for Management Docker, we will do:
- Pull and Run Docker Images
- Basic commands Docker
-  List containers
-  List docker images
-  Login into container
- Install Dry Tool
- Discovery Dry Tool

### Pull and Run Docker Images
Download "Hello World" and "Busybox" images:
```
docker pull hello-world
docker pull busybox 
```

We get output:
```
$ docker pull hello-world
Using default tag: latest
latest: Pulling from library/hello-world
1b930d010525: Pull complete 
Digest: sha256:9572f7cdcee8591948c2963463447a53466950b3fc15a247fcad1917ca215a2f
Status: Downloaded newer image for hello-world:latest
docker.io/library/hello-world:latest
```


Run Download Images:
```
docker run -t -d hello-world
docker run -t -d busybox
```
**What do -t and -d parameter?**

### Basic commands Docker
The Next commands will do to you more get familiar with Docker.
| List running containers | |
| ------ |----- |
| command: | ```docker ps``` |
| output: | ![alt text](https://i.ibb.co/SyJ7VPq/docker1.png) |


| List running containers with status exited | |
| ------- | ------ |
| command: | ```docker ps -a``` |
| output: | ![alt text](https://i.ibb.co/SyJ7VPq/docker1.png) |

| List images | |
| ------- | ------ |
| command: | ```docker images``` |
| output: | ![alt text](https://i.ibb.co/1st2rCy/docker2.png) |

| Login into containers | ------ |
| ----------------------- | ------ |
| command: | ```docker exec -it <id container> <comando a ejecutar en consola>``` |
| example: | ```docker exec -it f349 /bin/sh``` |
| output: | ```!# ```|

**what do -it parameter?**

## Install Dry Tool

```
curl -sSf https://moncho.github.io/dry/dryup.sh | sudo sh
sudo chmod 755 /usr/local/bin/dry
dry (Para ejecutar la herramienta)
```

## Discovery Dry Tool

You are free to explore Dry Tool like management and monitor for docker containers :D 

## Mini Challenge

Search, Pull, Run and Play Supermario image :D +3 Point 
