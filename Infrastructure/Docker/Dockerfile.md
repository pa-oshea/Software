```dockerfile
FROM image | scratch - base image for the build
MAINTAINER email - name of the maintainer (metadata)
COPY path dst - copy path from the context into the container at location dst
ADD src dst - same as copy but untar archives and accepts http urls
RUN arg... - run an arbitrary command insdie the container
USER name - set the default username
WORKDIR path - set the default working directory
CMD args... - set the default command
ENV name value - set an environment variable
```

##### Cache when building from docker image
Add the package manager file and run the install command before adding the app directory will cache the build modules for the application.

```Dockerfile
ADD package*.json ./
RUN npm install
ADD . .
```

This will cache the node_modules when building the docker image