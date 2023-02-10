The compose file is a [YAML](https://yaml.org) file defining services, networks, and volumes for a Docker application.
The compose specification allows one to define a platform-agnostic container based application. Such an application is designed as a set of containers which have to both run together with adequate shared resources and communication channels.

#### [Services](https://docs.docker.com/compose/compose-file/#services-top-level-element)
A service is an abstract concept implemented on platforms by running the same container image (and configuration) one or more times. Services communicate with each other through networks

#### [Networks](https://docs.docker.com/compose/compose-file/#networks-top-level-element)
In this specification, a network is a platform capability abstraction to establish an IP route between containers withing services connected together. Low-level, platform-specific networking options are grouped into the network definition and **may** be partially implemented on some platforms.

#### [Volumes](https://docs.docker.com/compose/compose-file/#volumes-top-level-element)
Services store and share persistent data into volumes. The specification describes such a persistent data as a high-level file system mount with global options. Actual platform-specific implementation details are grouped into the volumes definition and **may** be partially implemented on some platforms.

### Example
```yaml
services:
  frontend:
    image: awesome/webapp
    ports:
      - "443:8043"
    networks:
      - front-tier
      - back-tier
    configs:
      - httpd-config
    secrets:
      - server-certificate

  backend:
    image: awesome/database
    volumes:
      - db-data:/etc/data
    networks:
      - back-tier

volumes:
  db-data:
    driver: flocker
    driver_opts:
      size: "10GiB"

configs:
  httpd-config:
    external: true

secrets:
  server-certificate:
    external: true

networks:
  # The presence of these objects is sufficient to define them
  front-tier: {}
  back-tier: {}
```
