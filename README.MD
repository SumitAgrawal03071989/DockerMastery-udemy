# Docker Mastery

## Install Docker

Used convenient script to install docker.

```bash
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
```

- make sure that docker is running without sudo.
- so running "docker version" without sudo, should not return any error.

## Install docker machine

<https://docs.docker.com/machine/install-machine/>

## Install docker compose

<https://docs.docker.com/compose/install/>

## Building Image, Running docker build

```bash
docker image build -t customnginx .
```

## Persistent Data

