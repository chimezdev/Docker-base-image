# Slow Node

Se this repository for the detailed beginning 
https://github.com/chimezdev/Microservices-Container-Debugging.git

# Container Registries
A centralized hub image storage and version control.

## Overview

This is a very simple, bare-bones NodeJS project created for you to use with Docker. This is a variant of our simple-node project that takes a long time to build.
`DockerHub` A popular container registry run by Docker organisation

## Container Setup

## Local Setup

**_Note_**: This is only needed if you want to run the app locally. You don't need to install the dependencies or run the server if you are running the code inside a Docker container.

- Install dependencies: `npm install`
- Run server: `node server.js`

- Build image: `docker build .`
- Run container with image: `docker run {image_id}` where `image_id` can be retrieved by running `docker images` and found under the column `IMAGE ID`
- You can use the `-d` flag to run the container in the background. This will enable you to run other commands in your terminal while the container is running.

# BASE IMAGES
- Building container images takes time
- A faster approach is to adopt Base Images
- This involves building operations that stays the same across multiple build once and saving it and consecutively building any other operation from it.
- Base images reduce time that it takes to run redundant operations

# Creating base image
- create a new directory `mkdir {directory name}`
copy the Dockerfile to this directory `cp Dockerfile {directory name/}`
cd into the new directory
`code Dockerfile ` to open the dockerfile in VS Code
- Remove all the lines below "Finish installing Node dependencies" and replace it with `CMD ["node"]`
save it and run
`docker build -t {image name} . `
- push the build to your docker repo. See below for steps on how to do that.
- cd up out of the directory you created that you are in.
- open the other Dockerfile in the home directory
- remove every other lines up that were not removed in the other Dockerfile, leaving from the line, "Create app directory"
- add this line as first line:
`FROM {the repository you pushed the base image to}:latest`
- save the file and built it.

Now anytime any changes is made to the code, buiding should be faster.

## Container Teardown

- Remove container: `docker kill {container_id}` where `container_id` can be retrieved by running `docker ps` and found under the column `CONTAINER ID`

# Using DockerHub

- After creating an account on DockerHub, create a repository.
- To push docker images to repository, Run the following command in your terminal:
`docker login --username={your docker username}`
`docker tag {image name} {docker repo}`, you can get the image name you built by doing `docker images` .
`docker push {repo address}` will push you container image to the repository.

# GLOSSARY

# Term 	            Definition

`Base Image`	A set of common dependencies built into a Docker      image that acts as a starting point to build an application’s Docker images to reduce build times
`Container` 	Grouped software dependencies and packages that make it easier and more reliable to deploy software
`Container Registry` 	A centralized place to store container images
`Docker-compose` 	A tool used to run multiple Docker containers at once; often used to specify dependent relationships between containers
`Dockerfile` 	A file containing instructions on how to translate an application into an image that can be run in containers
`Ephemeral` 	Software property where an application is expected to be short-lived
`Image` 	A snapshot of dependencies and code used by Docker containers to run an application
`System Process`	A computer program run by the operating system
