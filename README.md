# docker-cheat-sheet
Quick reference guide for Docker commands
> Click :star:if you like the project. Pull Requests are highly appreciated. Follow me [@SudheerJonna](https://twitter.com/SudheerJonna) for technical updates.

### Table of Contents

| No. | Questions |
|---- | ---------
|1  | [**What is docker?**](#what-is-docker) |
|2  | [**Why docker?**](#why-docker)|
|3  | [**Installation**](#installation) |
|4  | [**Registries and Repositories**](#registries-and-repositories)|
|5  | [**Create,Run,Update and Delete containers**](#)|
|6  | [**Start and stop containers**](#start-and-stop-containers) |
|7  | [**Cleanup commands**](#cleanup-commands)|
|8  | [**Utility commands**](#utility-commands)|
|9  | [**Docker Hub**](#docker-hub)|

### What is docker?
   Docker is a tool designed to make it easier to create, deploy, and run applications by using containers.

   **[⬆ Back to Top](#table-of-contents)**

### Why docker?
   Docker is useful to automate the deployment of applications inside a software containers, which makes the applications easy to ship and run virtually anywhere (i.e, platform independent). The Docker container processes run on the host kernel, unlike VM which runs processes in guest kernel.

   ![dockervsvm](images/dockervsvm.jpg)

   **[⬆ Back to Top](#table-of-contents)**

### Installation?
The docker desktop downloads are available for windows, mac and linux distributions.

#### Windows
It supports for Windows 10 64-bit: Pro, Enterprise, or Education (Build 15063 or later) editions. You need to follow the below steps for installation.

1. Download docker desktop for windows from https://docs.docker.com/docker-for-windows/install/
2. Double-click `Docker Desktop Installer.exe` to run the installer.
3. Make sure `Enable Hyper-V Windows Features` option is selected

#### Mac

1. Download docker desktop for mac from https://docs.docker.com/docker-for-mac/install/
2. Double-click `Docker.dmg` to open the installer and drag it to the Applications folder.
3. Double-click `Docker.app` in the Applications folder to start Docker.

#### Linux

You can install from a package easily
1. Go to https://download.docker.com/linux/ubuntu/dists/, choose your Ubuntu version and then go to pool/stable/ to get .deb file
2. Install Docker Engine by referring the downloaded location of the Docker package.
```cmd
$ sudo dpkg -i /path/to/package.deb
```
3. Verify the Docker Engine by running the `hello-world` image to check correct installation.
```cmd
$ sudo docker run hello-world
```

   **[⬆ Back to Top](#table-of-contents)**

### Registries and Repositories
#### Registry:
Docker Registry is a service that stores your docker images. It could be hosted by a third party, as public or private registry. Some of the examples are,

- Docker Hub,
- Quay,
- Google Container Registry,
- AWS Container Registry

#### Repository:
A Docker Repository is a collection of related images with same name which have different tags. These tags are an alphanumeric identifiers(like 1.0 or latest) attached to images within a repository.

For example, if you want to pull golang image using `docker pull golang:latest` command, it will download the image tagged latest within the `golang` repository from the Docker Hub registry. The tags appeared on dockerhub as below,

#### Login
Login to a registry
```js
> docker login [OPTIONS] [SERVER]

[OPTIONS]:
-u/--username username
-p/--password password

Example:

1. docker login localhost:8080 // Login to a registry on your localhost
2. docker login
```

#### Logout
Logout from a registry
```js
> docker logout [SERVER]

Example:

docker logout localhost:8080 // Logout from a registry on your localhost
```

#### Search image
Search for an image in registry
```js
docker search [OPTIONS] TERM

Example:
docker search golang
docker search --filter stars=3 --no-trunc golang
```
#### Pull image

This command pulls an image or a repository from a registry to local machine

```js
docker image pull [OPTIONS] NAME[:TAG|@DIGEST]

Example:
docker image pull golang:latest
```
#### Push image

This command pushes an image to the registry from local machine.

```js
docker image push [OPTIONS] NAME[:TAG]
docker image push golang:latest
```

  **[⬆ Back to Top](#table-of-contents)**

### Create,Run,Update and Delete containers

#### Create
Create a new container
```cmd
docker container create [OPTIONS] IMAGE [COMMAND] [ARG...]

Example:
docker container create -t -i sudheerj/golang --name golang
```

#### Rename

Rename a container

```cmd
docker container rename CONTAINER NEW_NAME

Example:
docker container rename golang golanguage
docker container rename golanguage golang
```

#### Run

```cmd
docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]

Example:
docker container run -it --name golang -d sudheerj/golang
```

You can also run a command inside container
```cmd
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

Example:
docker exec -it golang sh // Or use bash command if sh is failed
```

#### Update
Update configuration of one or more containers

```cmd
docker container update [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container update --memory "1g" --cpuset-cpu "1" golang // update the golang to use 1g of memory and only use cpu core 1
```

#### Remove
Remove one or more containers

```cmd
docker container rm [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container rm golang
docker rm $(docker ps -q -f status=exited) // Remove all the stopped containers
```
  **[⬆ Back to Top](#table-of-contents)**
### Start and stop containers

#### Start
Start one or more stopped containers

```cmd
docker container start [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container start golang
```

### Stop
Stop one or more running containers


```cmd
docker container stop [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container stop golang
docker stop $(docker ps -a -q) // To stop all the containers
```

#### Restart
Restart one or more containers and processes running inside the container/containers.

```cmd
docker container restart [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container restart golang
```

#### Pause
Pause all processes within one or more containers

```cmd
docker container pause CONTAINER [CONTAINER...]

Example:
docker container pause golang
```

### Unpause/Resume
Unpause all processes within one or more containers

```cmd
docker container unpause CONTAINER [CONTAINER...]

Example:
docker container unpause golang
```

#### Kill
Kill one or more running containers

```cmd
docker container kill [OPTIONS] CONTAINER [CONTAINER...]

Example:
docker container kill golang
```

#### Wait
Block until one or more containers stop and print their exit codes after that


```cmd
docker container wait CONTAINER [CONTAINER...]

Example:
docker container wait golang
```
  **[⬆ Back to Top](#table-of-contents)**

### Cleanup commands

  **[⬆ Back to Top](#table-of-contents)**

### Utility commands

  **[⬆ Back to Top](#table-of-contents)**

### Docker Hub
   Docker Hub is a cloud-based repository provided by Docker to test, store and distribute container images which can be accessed either privately or publicly.
