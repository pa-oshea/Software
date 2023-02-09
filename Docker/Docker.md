Docker is an open-source containerization platform for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.

## Image
Docker image is an executable package of software that includes everything needed to run an application. The image informs how a container should instantiate, determining which software components will run and how.

## Container
A container is a sandboxed process on your machine that is isolated from all other processes on the host machine. That isolation leverages [kernal namespaces and cgroups](https://medium.com/@saschagrunert/demystifying-containers-part-i-kernel-space-2c53d6979504), features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use. To summarize, a container:
 - is a runnable instance of an image. You can create, start, stop, move or delete a container using the DockerAPI or CLI.
 - can be run on local machines, virtual machines or deployed to the cloud.
 - is portable (can be run on any OS).
 - is isolated from other containers and runs its own software, binaries and configurations.

### Difference between Docker containers and Virtual machines
#### Docker containers
 - Docker containers contain binaries, libraries, and configuration files along with the application itself.
 - They don't contain a guest OS for each container and rely on the underlying OS kernal, which makes the containers lightweight.
 - Containers share resources with other containers in the same host OS and provide OS-level process isolation.
#### Virtual machines
- Virtual machines run on Hypervisors, which allow multiple Virtual machines to run on a single machine along with its own operationg system.
- Each VM has its own copy of an operating system along with the application and necessary binaries, which makes it significantly larger and it requires more resources.
- They provide Hardware-level process isolation and are slow to boot.

### Important terminologies in Docker
#### Docker image
- It is a file, comprised of multiple layers, used to execute code in a docker container.
- They are a set of instructions used to create docker containers.

#### Container
- It is a runtime instance of an image.
- Allows developers to package applications with all parts needed such as libraries and other dependencies.

#### Dockerfile
- It is a text document that contains necessary commands which on execution helps assemble a Docker image
- Docker image is created using a Dockerfile

#### Docker engine
- The software that hosts the container is named Docker engine.
- Docker engine is a client-server based application.
- The docker engine has **3 main** components:
	- **Server**: it is responsible for creating and managing Docker images, containers, networks, and volumes on Docker. It is referred to as a daemon process.
	- **REST API**: It specifies how the application can interact with the server and instructs it what to do.
	- **Cilent**: The client is a docker command-line interface (CLI), that allows us to interact with docker using the docker commands.

#### Docker hub
- Docker hub is the offical online repository where you can find other Docker images that are available for use.
- It makes it easy to find, manage, and share containers images with others.