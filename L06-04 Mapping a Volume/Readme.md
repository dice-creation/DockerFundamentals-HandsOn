## create a volume

    docker volume create myvol

## inspect the volume

    docker volume inspect myvol

## list the volumes

    docker volume ls

## run a container with a volume

    docker run -d --name devtest -v myvol:/app nginx:latest


## connect to the instance

    docker exec -it devtest bash

## Let's create a file in the volume using Vim

    apt-get update
    apt-get install vim
    cd app
    vim test.txt >> hello world!

## Delete the volume 

    docker stop devtest
    docker rm devtest

## Run it again

    docker run -d --name devtest -v myvol:/app nginx:latest
    docker exec -it devtest bash
    cd app
    cat test.txt

## Stop and remove the container
    # need to stop containers using myvol
    docker stop devtest
    docker rm devtest

    docker volume rm myvol

Mapping to a local folder
## run a container with a volume

    docker run -d --name devtest -v d:/test:/app nginx:latest

## inspect the container

    docker inspect devtest