# L05-04

Type the following Docker commands:

## Pull and run a Nginx server
    Mapping port local 80 to exposed 8080 and naming it webserver with the image nginx
    docker run -d -p 8080:80 --name webserver nginx

## List the running containers

    docker ps

## List the images

    docker images

## Attach to the container
    docker run -it nginx -- /bin/bash               Attach Shell
    docker run -it -- microsoft/powershell:nanoserverpwsh.exe   Attach Powershell
    docker container exec -it webserver bash  

Exit by typing

    exit

## Stop the container

    docker stop webserver

## Remove the container from memory
    docker rm $(docker ps -a -q)                Removes all stopped containiers
    docker rm webserver

## Remove the image
    docker images
    docker rmi nginx

## Removes all images not in use by any container
    !! be careful
    docker system prune -a