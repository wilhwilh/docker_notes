# docker_notes
Notes from course of docker

command: docker version
    verified cli can talk to engine

command: docker info
    most config values of engine

docker command line structure
    new format: docker <command> <sub-command> (option)
    old way: docker <command> (options)

docker container run --publish 80:80 nginx
    - searck locally the image of nginx if dosent exist is donwloaded from docker hub
    - started a new container from that image
    - Opened port 80 on the host IP
    - Routes that traffic to the container IP, port 80
    - Keep runing in the command line

docker container run --publish 80:80 --detach nginx
    - <--detach> started the container in background

docker container ls
    - List the container active
    - Add <-a> to see all containers

** name of container are random and unique

docker container run --publish 80:80 --detach --name webhost nginx
    - <--name <name> > to indicate manually the name of the container

docker container logs webhost
    - show the logs of the container with the name webhost

docker container top webhost
    - show the proccess running inside the container

docker container rm <firts three character of the id>
    - remove the container
    - if a container if runninf, can add <-f> to force remove container, else we must stop the container before

docker container top - process list in one container
docker container inspect - details of one container config
docker container stats - performance statsfor all containers in real time
    
----------------------- INSIDE ----------------------------------

docker container run it - star new container interactively
docker container exec it - run a dditional command in a existing container

docker network ls - show networks

----------------------- DATA -----------------------

docker container  -v //c/Users/<user_name>/stuff:/path/container (windows) the path is inside "

docker container  -v /Users/<user_name>/stuff:/path/container (mac/linux)