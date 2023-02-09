### Common commands
| command | description |
| -------------- | - |
| docker build \[[options](https://docs.docker.com/engine/reference/commandline/build/#options)\] \<[path](https://docs.docker.com/engine/reference/commandline/build/#build-with-path)\> \| \<[url](https://docs.docker.com/engine/reference/commandline/build/#build-with-url)\> \| [-](https://docs.docker.com/engine/reference/commandline/build/#build-with--) | Build an image from a dockerfile | 
| docker run \[[options](https://docs.docker.com/engine/reference/commandline/run/#options)\] \<image\> \<command\> \[args...\]| Run an image |
| docker ps \[[options](https://docs.docker.com/engine/reference/commandline/ps/#options)\] | List running containers |
| docker rm \[[options](https://docs.docker.com/engine/reference/commandline/rm/#options)\] \[\<contianer(s)\>\] | Remove container |
| docker stop \[[options](https://docs.docker.com/engine/reference/commandline/stop/#options)\] \[\<container>] | Stop container |
| docker rm $(docker ps -aq) | Remove all stop containers. (Will fail if container running) -f to stop running containers |
| docker rmi \[[options](https://docs.docker.com/engine/reference/commandline/rmi/#options)\] \[\<image>] | Remove image |
| docker stop \<container\> | Stop container |
| docker exec \[[options](https://docs.docker.com/engine/reference/commandline/exec/#options)\] \<container\> \<command\> \[args...\] | Run a new command in a running container. |
| docker exec -it \<container\> sh | Run an interactive shell in the container |
| docker logs \[[options](https://docs.docker.com/engine/reference/commandline/logs/#options)] \<container\> | Fetch the logs of a container |

### Docker run common options
| option | description |
| - | - |
| --detach, -d | Run container in background and print container ID. |
| --publish, -p \<host-port\>:\<container-port\> | Publish a container's port(s) to the host. |
| --name | Assign a name to the container. |
| --volume, -v \<src>:\<dst> | Bind mount a volume |



