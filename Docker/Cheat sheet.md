### Dockerfile
| command | description |
| --- | --- |
| **FROM** *image/scratch* | base image for the build |
| **MAINTAINER** *email* | name of the maintainer (metadata) |
| **COPY** *path* *dst* | copy *path* from the context into the containter at location *dst* |
| **ADD** *src* *dst* | same as **COPY** but untar archives and accepts http urls |
| **RUN** *args...* | run an arbitrary command inside the container |
| **USER** *name* | set the default username |
| **WORKDIR** *path* | set the default working directory |
| **CMD** *args...* | set the default command |
| **ENV** *name value* | set an environment variable |


