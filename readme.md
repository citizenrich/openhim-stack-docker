# Quickstart using Docker for the OpenHIM stack

> Note: The maintainers now provide a docker-compose file for the stack, see: https://github.com/jembi/openhim-console in the infrastructure folder.

OpenHIM requires the [openhim-core api server](https://github.com/jembi/openhim-core-js), mongodb, and an administrative [console](https://github.com/jembi/openhim-console) run by a web server.

## How to use

This simple docker-compose file fires up the stack, such as for a developer environment.

```
git clone https://github.com/citizenrich/openhim-stack-docker
cd openhim-stack-docker
docker-compose up -d
# check out the running containers
docker ps
```

Visit https://localhost:8081

The web browser will probably complain about a lack of security because a self-signed certificate is being used. Click through. Log in with root@openhim.org and openhim-password. There will probably a failure again because of a self-signed cert, so follow the link and it will then work.

Thanks for the support from Jembi in this [issue](https://github.com/jembi/openhim-docker/issues/1).
