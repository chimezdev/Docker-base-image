# Slow Node

## Overview

This is a very simple, bare-bones NodeJS project created for you to use with Docker. This is a variant of our simple-node project that takes a long time to build.

## Local Setup

**_Note_**: This is only needed if you want to run the app locally. You don't need to install the dependencies or run the server if you are running the code inside a Docker container.

- Install dependencies: `npm install`
- Run server: `node server.js`

## Container Setup

- Build image: `docker build .`
- Run container with image: `docker run {image_id}` where `image_id` can be retrieved by running `docker images` and found under the column `IMAGE ID`
- You can use the `-d` flag to run the container in the background. This will enable you to run other commands in your terminal while the container is running.

## Container Teardown

- Remove container: `docker kill {container_id}` where `container_id` can be retrieved by running `docker ps` and found under the column `CONTAINER ID`

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