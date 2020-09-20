<!-- markdownlint-disable -->
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




## Volums

```bash
# Start mysql server with root user and password set to root1
docker container run -d --name mysql -e MYSQL_ROOT_PASSWORD=root1 -p 3306:3306 -v mysql-db:/var/lib/mysql mysql
```
## Assignment: named volumes

```
docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d -v postgres-db:/var/lib/postgresdb postgres:9.6.1 
```

## Assignment: create docker image to run simple java application

- install java
```bash
sudo apt install openjdk-11-jre-headless
sudo apt install default-jdk
java -version
```
- install maven
```bash
sudo apt update
sudo apt install maven
```
- Create a java project to print message on screen.
- Test the jar is running with this command

```bash
java -cp SimpleJavaProject-1.0-SNAPSHOT.jar org.example.MainApp
```
Create a docker file as below
```
FROM java:8
WORKDIR /
ADD SimpleJavaProject-1.0-SNAPSHOT.jar SimpleJavaProject-1.0-SNAPSHOT.jar
EXPOSE 8080
CMD java -cp SimpleJavaProject-1.0-SNAPSHOT.jar org.example.MainApp
```
- build image from docker file mentioned above
```
docker build -t sumitagrawal4548/helloworld .
```
- Start container in interactive mode with above image.



## Install Kubernetes 

https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#1-overview

```
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
  
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client

sudo microk8s kubectl get all --all-namespaces
```
https://10.152.183.152:443

/snap/bin/microk8s.enable dns