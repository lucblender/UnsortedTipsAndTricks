# Docker help
## General
### build image
sudo docker build -t dlmsmain:1.0 .

### show images
docker images

### remove image
sudo docker rmi image:version

### remove <none> <none> images
sudo docker system prune

### test image localy 
sudo docker run -it dlmsmain:1.0

### Tag image to be able to upload it to the registry on the gridlapep server.
sudo docker tag dlmsmain:1.2 vlegridlabep.hevs.ch/dlmsmain:1.2

### Login to the gridlapep registry.
sudo docker login vlegridlabep.hevs.ch

### Push the image to the registry.
sudo docker push vlegridlabep.hevs.ch/dlmsmain:1.2

## Volumes

### create a volume
sudo docker volume create certificates

### list all volume
sudo docker volume ls

### inspect a volume
sudo docker volume inspect certificates

### remove unused volume
sudo docker volume prune

### launch with volume
sudo docker run -v certificates:/certificates/ -it image:version

### get volume used by a container
docker inspect --format="{{.Mounts}}" $containerID

## Others

### get list of exited docker 
docker ps --filter "status=exited"

### remove all exited docker
sudo docker ps -a | grep Exit | cut -d ' ' -f 1 | xargs sudo docker rm

### Launch shell on running docker
sudo docker exec -it f31 /bin/sh

