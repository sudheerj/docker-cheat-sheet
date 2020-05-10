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
|5  | [**Start and stop containers**](#start-and-stop-containers) |
|6  | [**Cleanup commands**](#cleanup-commands)|
|7  | [**Utility commands**](#utility-commands)|

### What is docker?
   Docker is a tool designed to make it easier to create, deploy, and run applications by using containers.

   **[⬆ Back to Top](#table-of-contents)**

### Why docker?

   **[⬆ Back to Top](#table-of-contents)**

### Installation?

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

1. docker login localhost:8080
2. docker login
```

#### Logout
Logout from a registry
```js
> docker logout [SERVER]

Example:

docker logout localhost:8080
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

### Start and stop containers

  **[⬆ Back to Top](#table-of-contents)**

### Cleanup commands

  **[⬆ Back to Top](#table-of-contents)**

### Utility commands

  **[⬆ Back to Top](#table-of-contents)**
