# Introduction

### Welcome to the containers! 

This repository serves as a central hub for storing Docker files required for various projects or applications. Whether you're working on software development, testing, or deployment tasks, having a centralized repository for Docker images can streamline your workflow and ensure consistency across environments.

## Purpose
The primary purpose of this repository is to:

- Store Docker files for different services, tools, and dependencies.
- Facilitate easy access and sharing of Docker images among team members.
- Enable quick setup and deployment of development, testing, and production environments.
- Ensure version control and traceability of Docker images used in different projects.

Docker usefull commands

list all images

```bash
docker images -a 
```

listt all volumes 

```bash
docker volume ls
```

List all containers. if you only want to list containers that are running, use this command `docker ps`


```bash
docker ps -a
```

Stop all containers 

```bash
docker stop $(docker ps -a -q)
```

Delete all containers 

```bash
docker system prune 

# or

docker rm  -f $(docker ps -a -q)
```