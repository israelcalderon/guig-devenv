# Guig! 
### Grphical User Interface for Git

This is only a demo application written in Python flask Vue JS stack. The server side microservice is a Flask "api REST" and the front js app microservice is a Vue app. This repository cotains the docker-compose and Dockerfiles needed in order to install and test all the environment, please follow the instructions below

## Prerequisites

- Docker CE 
```shell
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
```
- docker-compose: please refer to https://docs.docker.com/compose/install/
- Linux OS is not required but I highly recommend it, in fact this environment has only be tested in linux

## Installing
1. Clone this repo in the directory of your preference

```shell
$ git clone git@github.com:israelcalderon/guig-devenv.git
```

2. Build the docker images and create the containers
```shell
$ cd guig-devenv
$ docker-compose up -d
```

3. We are ready to go! Open your web browser and go to the following URL:
```
http://127.0.0.1:8080/
```

Would you like to see the apps code? please refer to their respective repositories:
```
https://github.com/israelcalderon/guig-back
https://github.com/israelcalderon/guig-front
```

In this repo you'll find nothing more thant the docker files for handling the project installation.

TODOS:
- Add docker bind volumes in code directories
- Add a reverse proxy with nginx
- Install uWSGI or Gunicorn for api serve

happy coding!