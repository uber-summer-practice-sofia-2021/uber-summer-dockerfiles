# uber-summer-dockerfiles
Dockerfiles and set-up instructions for container-based development in different languages.
## Description

This is a collection of Docker and Docker Compose environment specifications aimed at easy and quick onboarding to development within a Docker container. This allows for unified dependency management across different team members, and overall quick set up when starting a new project.

The idea is that the Docker image can be used in development and afterwards deployment on AWS or similar cloud provider. The Docker Compose file spawns a (mostly) hot-reloading environment, where the ports used by each container are being exposed on the host machine.

The example project for each programming language creates a web server running at port 5000. The `/` endpoint on each server returns Hello World.

| Environment | Docker image | Docker Compose File | Hot reload available |
|-------------|--------------|---------------------|----------------------|
| Python      | ✔️            | ✔️                   | ✔️                    |
| Node JS     | ✔️            | ✔️                   | ✔️                    |
| Java        | ✔️            | ✔️                   | ❌                    |
| Go          | ✔️            | ✔️                   | ✔️                    |

## Getting Started

Before starting please get familiar with what [Docker](https://docs.docker.com/get-started/overview/) and [Docker Compose](https://docs.docker.com/compose/) are.

[This](https://runnable.com/blog/a-better-dev-workflow-with-docker-compose) is also a good overview of pros and cons when using Docker Compose for local development.

### Dependencies

* [Docker](https://www.docker.com/products/docker-desktop)
* Port 5000 being available on host machine

### Usage

After installing Docker pick the programming language environment which you want to use and in the directory run:
```
docker compose up -d
```
This will spawn the running container in the background. When you then make changes to the code in the folder you will see the changes being reflected at `localhost:5000`.

To de-spawn the environment and remove the running containers execute:
```
docker compose down
```
