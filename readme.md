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


## Another approach using caddy webserver

The official image for the console uses the nginx server. docker-compose-prev is an example for using the caddy webserver. The console app needs to be either built using node or a prebuilt release downloaded.

Prepare the prebuilt release. Follow the [instructions](https://github.com/jembi/openhim-console):

On Unix-like systems:
```shell
mkdir openhim-console-prebuilt
cd openhim-console-prebuilt
wget https://github.com/jembi/openhim-console/releases/download/v1.10.0/openhim-console-v1.10.0.tar.gz
# or get the master, ie.
# wget https://github.com/jembi/openhim-console/archive/master.tar.gz
tar -vxzf openhim-console-v1.10.0.tar.gz
```

### Fire it up

```
cd ../
git clone https://github.com/citizenrich/openhim-stack-docker
cd ../openhim-stack-docker
docker-compose up -d
```

Thanks for the support from Jembi in this [issue](https://github.com/jembi/openhim-docker/issues/1).
