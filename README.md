# Docker Notes
My own docker notes from following the official tutorial at https://docs.docker.com/get-started/
Based on ubuntu 5.0.0-29-generic

## Installation and configuration
See "docker_installation_procedures" and "docker_notes".

## Part 1, 2 - Introduction and Containers
Container - code and dependencies packaged so that it can be quickly and easily moved to another system

Container images become containers at runtime (in the docker engine).
Faster than VMs because containers virtualize OS instead of hardware.

### Hierarchy of an App
1. Container (bottom)
  Single instance running your software
2. Service
  How containers behave in production (combination of mulitple containers of a single image)
3. Stack
  Defines interaction of multiple services (multiple images)

### Dockerfile
Dockerfile - A portable image with appcode, dependencies, runtime. All travels together
  * Defines what goes on in environment inside container
  * resources (network interfaces, disk drives, etc.) virutalized, so need to map ports, specify which files to copy in

### Dockerhub
Images can be pushed to dockerhub and run from any device.

### Commands
1. List images
`docker image ls`
2. List all containers (including stopped containers)
`docker container ls -all`
3. Create a docker image
`docker build --tag=<image-name>`
4. Run a container
`docker run <image-name>`
5. Run a docker container in detatched mode
`docker run -d <image-name>`
6. Run a docker container with ports exposed
`docker run -p <host-port>:<container-port> <image-name>`
7. Stop a container
`docker container stop <container-ID>`
8. Login to dockerhub
`docker login`
9. Tag an image
`docker tag <image-name> <username>/<repository>:<tag>`
10. Publish an image
`docker push <username>/<repository>:<tag>`
