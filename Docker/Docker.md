Docker is an open-source containerization platform for automating the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises.

## Container
A container is a sandboxed process on your machine that is isolated from all other processes on the host machine. That isolation leverages [kernal namespaces and cgroups](https://medium.com/@saschagrunert/demystifying-containers-part-i-kernel-space-2c53d6979504), features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use. To summarize, a container:
 - is a runnable instance of an image. You can create, start, stop, move or delete a container using the DockerAPI or CLI.
 - can be run on local machines, virtual machines or deployed to the cloud.
 - is portable (can be run on any OS).
 - is isolated from other containers and runs its own software, binaries and configurations.