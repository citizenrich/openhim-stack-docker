# Quickstart using Docker for the OpenHIM stack

> Note: This repo will not be updated. The maintainers now provide a docker-compose file for the stack, see: https://github.com/jembi/openhim-console in the infrastructure folder. Use of that file is advised.


Thanks for the support from Jembi in this [issue](https://github.com/jembi/openhim-docker/issues/1).

OpenHIM requires the [openhim-core api server](https://github.com/jembi/openhim-core-js), mongodb, administrative [console](https://github.com/jembi/openhim-console), and a web server to run the console. This uses the awesome and simple [Caddy](https://caddyserver.com).

This simple docker-compose file fires up the stack, such as for a developer environment.

## How to use

It uses the official [openhim-core](https://github.com/jembi/openhim-docker) Docker image, the official mongo image, and Caddy web server. The console app needs to be either built using node or a prebuilt release downloaded.

The file docker-compose.yml uses the prebuilt release. The docker-compose file instructs Docker to mount some volumes. There are two directories used, 'openhim-console-prebuilt' which will hold the prebuilt release that is served, and the clone of this repo.


### Using the prebuilt release

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

Visit https://localhost:8081

The web browser will probably complain about a lack of security because a self-signed certificate is being used. Click through. Log in with root@openhim.org and openhim-password. There will probably a failure again because of a self-signed cert, so follow the link and it will then work.
